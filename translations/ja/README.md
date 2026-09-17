![Material design library logo](images/logo.png)

<!-- github-global:langs:start -->
[简体中文](../zh-CN/README.md) | [繁體中文](../zh-TW/README.md) | [日本語](./README.md)
<!-- github-global:langs:end -->


# Material Design Android Library

<a href="https://play.google.com/store/apps/details?id=com.gc.demomaterialdesign">
  <img alt="Android app on Google Play" src="https://developer.android.com/images/brand/en_app_rgb_wo_45.png" />
</a>


[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-Material%20Design%20Android%20Library-brightgreen.svg?style=flat)](https://android-arsenal.com/details/1/1156)

* [使い方](#howtouse)
* [コンポーネント](#components)
    * [ボタン](#buttons)
        * [フラットボタン](#flat-button)
        * [レクタングルボタン](#rectangle-button)
        * [フロートボタン](#float-button)
        * [フロートスモールボタン](#float-small-button)
    * [スイッチ](#switches)
        * [CheckBox](#checkbox)
        * [Switch](#switch)
    * [プログレスインジケーター](#progress-indicators)
        * [プログレスバー（円形・不確定）](#progress-bar-circula-rindeterminate)
        * [プログレスバー（不確定）](#progress-bar-indeterminate)
        * [プログレスバー（不確定・確定）](#progress-bar-indeterminate-determinate)
        * [プログレスバー（確定）](#progress-bar-determinate)
        * [スライダー](#slider)
        * [数値インジケーター付きスライダー](#slider-with-number-indicator)
* [ウィジェット](#widgets)
    * [SnackBar](#snackbar)
    * [Dialog](#dialog)
    * [カラーセレクター](#color-selector)

## 使い方

このライブラリを使用するには、MaterialDesign プロジェクトをダウンロードし、ワークスペースにインポートして、Android プロジェクトの設定でライブラリとして追加するだけです。

お好みであれば、gradle の依存関係を使用することもできます。build.gradle ファイルに以下の行を追加してください:

```xml
repositories {
    jcenter()
}

dependencies {
    compile 'com.github.navasmdc:MaterialDesign:1.+@aar'
}
```

一部のコンポーネントにはカスタム属性があります。これらを使用する場合は、xml ファイルの最初のコンポーネントに次の行を追加する必要があります:

```xml
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:materialdesign="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    >
</RelativeLayout>
```

>ScrollView を使用する予定がある場合は、カスタムコンポーネントでの問題を避けるため、このライブラリに含まれている CustomScrollView を使用することをお勧めします。
>このコンポーネントを使用するには:
>```xml
><com.gc.materialdesign.views.ScrollView 
>    xmlns:android="http://schemas.android.com/apk/res/android"
>    xmlns:materialdesign="http://schemas.android.com/apk/res-auto"
>    android:id="@+id/scroll"
>    android:layout_width="match_parent"
>    android:layout_height="match_parent">
></com.gc.materialdesign.views.ScrollView>
>```

##コンポーネント

####ボタン

######フラットボタン

![flat button](images/flat_button.png)
```xml
<com.gc.materialdesign.views.ButtonFlat
                android:id="@+id/buttonflat"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:background="#1E88E5"
                android:text="Button" />
```

######レクタングルボタン

![rectangle button](images/rectangle_button.png)
```xml
<com.gc.materialdesign.views.ButtonRectangle
                android:id="@+id/button"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:background="#1E88E5"
                android:text="Button" />
```

######フロートボタン

![float button](images/float_button.png)

>このコンポーネントは画面の右下に配置することをお勧めします。このコンポーネントを使用するには、xml ファイルに次のコードを記述してください。
>アニメーション付きでこのコンポーネントを開始したくない場合は、animate 属性を false に設定してください。
>このコンポーネントの drawable アイコンを設定するには、icon 属性にアイコンを指定してください。

```xml
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:materialdesign="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    >
    <!-- ... XML CODE -->
    <com.gc.materialdesign.views.ButtonFloat
                android:id="@+id/buttonFloat"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_alignParentRight="true"
                android:layout_alignParentBottom="true"
                android:layout_marginRight="24dp"
                android:background="#1E88E5"
                materialdesign:animate="true"
                materialdesign:iconDrawable="@drawable/ic_action_new" />
</RelativeLayout>
```

######フロートスモールボタン

![float small button](images/float_small_button.png)

```xml
<com.gc.materialdesign.views.ButtonFloatSmall
                android:id="@+id/buttonFloatSmall"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:background="#1E88E5"
                materialdesign:iconDrawable="@drawable/ic_action_new" />
```

####スイッチ

######CheckBox
![checkbox](images/checkbox.png)

```xml
<com.gc.materialdesign.views.CheckBox
                android:id="@+id/checkBox"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:background="#1E88E5"
                materialdesign:check="true" />
```

######Switch
![switch](images/switch.png)

```xml
<com.gc.materialdesign.views.Switch
                android:id="@+id/switchView"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:background="#1E88E5"
                materialdesign:check="true" />
```

####プログレスインジケーター

######プログレスバー（円形・不確定）
![progress bar circular indeterminate](images/progress_bar_circular_indeterminate.png)

```xml
<com.gc.materialdesign.views.ProgressBarCircularIndeterminate
                android:id="@+id/progressBarCircularIndeterminate"
                android:layout_width="32dp"
                android:layout_height="32dp"
                android:background="#1E88E5" />
```

######プログレスバー（不確定）
![progress bar indeterminate](images/progress_bar_indeterminate.png)

```xml
<com.gc.materialdesign.views.ProgressBarIndeterminate
                android:id="@+id/progressBarIndeterminate"
                android:layout_width="fill_parent"
                android:layout_height="wrap_content"
                android:background="#1E88E5" />
```

######プログレスバー（不確定・確定）
![Progress bar indeterminate determinate](images/progress_bar_indeterminate_determinate.png)


```xml
<com.gc.materialdesign.views.ProgressBarIndeterminateDeterminate
                android:id="@+id/progressBarIndeterminateDeterminate"
                android:layout_width="fill_parent"
                android:layout_height="wrap_content"
                android:background="#1E88E5" />
```

>プログレスを開始するには、progress を設定するだけです。
>
>```java
>progressBarIndeterminateDeterminate.setProgress(progress);
>```

######プログレスバー（確定）
![Progress bar determinate](images/progress_bar_determinate.png)


```xml
<com.gc.materialdesign.views.ProgressBarDeterminate
                android:id="@+id/progressDeterminate"
                android:layout_width="fill_parent"
                android:layout_height="wrap_content"
                android:background="#1E88E5" />
```

>`materialdesign:max="50"` および `materialdesign:min="25"` 属性を使用して、プログレスの最大値と最小値をカスタマイズできます。

######スライダー
![Slider](images/slider.png)


```xml
<com.gc.materialdesign.views.Slider
                android:id="@+id/slider"
                android:layout_width="fill_parent"
                android:layout_height="wrap_content"
                android:background="#1E88E5"
                materialdesign:max="50"
                materialdesign:min="0"
                 />
```

######数値インジケーター付きスライダー
![Slider with number indicator](images/slider_with_number_indicator.png)


```xml
<com.gc.materialdesign.views.Slider
                android:id="@+id/slider"
                android:layout_width="fill_parent"
                android:layout_height="wrap_content"
                android:background="#1E88E5"
                materialdesign:max="50"
                materialdesign:min="0"
                materialdesign:showNumberIndicator="true"/>
```

##ウィジェット

####SnackBar

![Snackbar](images/snackbar.png)


```java
SnackBar snackbar = new SnackBar(Activity activity, String text, String buttonText, View.OnClickListener onClickListener);
snackbar.show();
```

> ボタンを表示したくない場合は、`buttonText` 属性に `null` を指定してください。

####Dialog

![Dialog](images/dialog.png)

```java
Dialog dialog = new Dialog(Context context,String title, String message);
dialog.show();
```

>イベントリスナーで accept ボタンと cancel ボタンを設定したり、そのテキストを変更したりできます。
>```java
> // accept ボタンのクリックリスナーを設定
>dialog.setOnAcceptButtonClickListener(View.OnClickListener onAcceptButtonClickListener);
> // cancel ボタンのクリックリスナーを設定
>dialog.setOnCancelButtonClickListener(View.OnClickListener onCancelButtonClickListener);
> // accept ボタンへのアクセス
>ButtonFlat acceptButton = dialog.getButtonAccept();
> // cancel ボタンへのアクセス
>ButtonFlat cancelButton = dialog.getButtonCancel();
>```

####カラーセレクター

![Color selector](images/color_selector.png)

```java
ColorSelector colorSelector = new ColorSelector(Context context,int intialColor, OnColorSelectedListener onColorSelectedListener);
colorSelector.show();
```