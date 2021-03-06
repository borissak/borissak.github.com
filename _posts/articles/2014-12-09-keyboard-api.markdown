---
layout: article
title: "안드로이드 키보드 관련 정리"
excerpt: "안드로이드 키보드 관련 개발을 위해서 관련 API를 모아보았습니다."
image: 
  thumb: # Grid에서 표시할때 노출되는?? 아닌가요?!
  teaser: # 
  feature: # 페이지 상단에 노출 되는 이미지 
category: articles
tags: [안드로이드, 키보드]
---

키보드 앱을 개발할것은 아니지만 키보드관련해서 필요한 항목들이 있었다. 
일반적으로 키보드를 올리고 내리는것을 포함해서 키보드 종류?와 패키지를 확인하고 싶었다. 

일부 내용은 [안드로이드 펍](http://www.androidpub.com/1104990)의 내용을 참조하였습니다.

### 하드웨어 키보드인가? (*확인 X*)
{% highlight java %}
private boolean isHardwareKeyboardAvailable() {
  return getResources().getConfiguration().keyboard != Configuration.KEYBOARD_NOKEYS;
}
{% endhighlight %}

### 현재 키패드 패키지 이름 가져오기
{% highlight java %}
private String getCurrentKeyboardPackage() {
  InputMethodManager imm = (InputMethodManager) getSystemService(Context.INPUT_METHOD_SERVICE);
  List<InputMethodInfo> mInputMethodProperties = imm.getEnabledInputMethodList();

  final int N = mInputMethodProperties.size();

  for (int i = 0; i < N; i++) {
    InputMethodInfo imi = mInputMethodProperties.get(i);

    String defaultInputMethod = Settings.Secure.getString(getContentResolver(),
        Settings.Secure.DEFAULT_INPUT_METHOD);
    if (imi.getId().equals(defaultInputMethod)) {
      return imi.getPackageName();
    }
  }
  return null;
}
{% endhighlight %}


### 키보드 감추기
{% highlight java %}
EditText editText = (EditText) findViewById(R.id.myEdit);
InputMethodManager imm = (InputMethodManager)getSystemService(Context.INPUT_METHOD_SERVICE);
imm.hideSoftInputFromWindow(editText.getWindowToken(), 0);
{% endhighlight %}

### 키보드 보여주기
{% highlight java %}
EditText editText = (EditText) findViewById(R.id.myEdit);
InputMethodManager imm = (InputMethodManager) getSystemService(Context.INPUT_METHOD_SERVICE);
imm.showSoftInput(editText, InputMethodManager.SHOW_FORCED);
or
imm.showSoftInputFromInputMethod (editText.getApplicationWindowToken(),InputMethodManager.SHOW_FORCED);
{% endhighlight %}

### 키보드 토글 - 위 두가지 방법으로 안되는 경우 다음과 같은 코드로 동작하는 경우가 있습니다.
{% highlight java %}
imm.toggleSoftInputFromWindow(editText.getApplicationWindowToken(),  InputMethodManager.SHOW_FORCED, 0); 
{% endhighlight %}

### 액티비티 시작시 자동으로 키보드 보여주기
AndroidManifest.xml의 activity 태그의 속성에 android:windowSoftInputMode = "stateVisible" 혹은 "stateAlwaysVisible"삽입

### 액티비티 시작시 자동으로 키보드 보여주지 않기
AndroidManifest.xml의 activity 태그의 속성에 android:windowSoftInputMode = "stateHidden" 혹은 "stateAlwaysHidden" 삽입

### 에디트 텍스트 선택해도 키보드 안뜨게 하기
EditText xml 속성에서 inputType 을 0으로 주면 안뜹니다.

