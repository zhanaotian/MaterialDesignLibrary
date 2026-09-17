![Material design library logo](images/logo.png)

<!-- github-global:langs:start -->
[简体中文](../zh-CN/README.md) | [繁體中文](./README.md) | [日本語](../ja/README.md)
<!-- github-global:langs:end -->


# Material Design Android Library

<a href="https://play.google.com/store/apps/details?id=com.gc.demomaterialdesign">
  <img alt="Android app on Google Play" src="https://developer.android.com/images/brand/en_app_rgb_wo_45.png" />
</a>


[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-Material%20Design%20Android%20Library-brightgreen.svg?style=flat)](https://android-arsenal.com/details/1/1156)

* [如何使用](#howtouse)
* [元件](#components)
    * [按鈕](#buttons)
        * [扁平按鈕（Flat Button）](#flat-button)
        * [矩形按鈕（Rectangle Button）](#rectangle-button)
        * [浮動按鈕（Float Button）](#float-button)
        * [小型浮動按鈕（Float small button）](#float-small-button)
    * [開關](#switches)
        * [CheckBox](#checkbox)
        * [Switch](#switch)
    * [進度指示器](#progress-indicators)
        * [圓形不確定進度條](#progress-bar-circula-rindeterminate)
        * [不確定進度條](#progress-bar-indeterminate)
        * [不確定／確定進度條](#progress-bar-indeterminate-determinate)
        * [確定進度條](#progress-bar-determinate)
        * [滑桿（Slider）](#slider)
        * [帶數字指示器的滑桿](#slider-with-number-indicator)
* [小工具](#widgets)
    * [SnackBar](#snackbar)
    * [Dialog](#dialog)
    * [顏色選擇器](#color-selector)

## 如何使用

如果你想使用這個函式庫，只需要下載 MaterialDesign 專案，將它匯入你的工作區，並在你的 Android 專案設定中將該專案加入為函式庫。

如果你偏好的話，也可以使用 gradle 相依性，只需在你的 build.gradle 檔案中加入以下幾行：

```xml
repositories {
    jcenter()
}

dependencies {
    compile 'com.github.navasmdc:MaterialDesign:1.+@aar'
}
```

有些元件具有自訂屬性，如果你想使用它們，必須在你的 xml 檔案的第一個元件中加入這一行：

```xml
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:materialdesign="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    >
</RelativeLayout>
```

>如果你要使用 ScrollView，建議使用這個函式庫提供的 CustomScrollView，以避免自訂元件產生問題。
>使用這個元件的方式：
>```xml
><com.gc.materialdesign.views.ScrollView 
>    xmlns:android="http://schemas.android.com/apk/res/android"
>    xmlns:materialdesign="http://schemas.android.com/apk/res-auto"
>    android:id="@+id/scroll"
>    android:layout_width="match_parent"
>    android:layout_height="match_parent">
></com.gc.materialdesign.views.ScrollView>
>```

##元件

####按鈕

######扁平按鈕（Flat Button）

![flat button](images/flat_button.png)
```xml
<com.gc.materialdesign.views.ButtonFlat
                android:id="@+id/buttonflat"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:background="#1E88E5"
                android:text="Button" />
```

######矩形按鈕（Rectangle Button）

![rectangle button](images/rectangle_button.png)
```xml
<com.gc.materialdesign.views.ButtonRectangle
                android:id="@+id/button"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:background="#1E88E5"
                android:text="Button" />
```

######浮動按鈕（Float Button）

![float button](images/float_button.png)

>建議將這個元件放在螢幕的右下角。要使用這個元件，請在你的 xml 檔案中撰寫以下程式碼。
>如果你不想讓這個元件以動畫方式啟動，請將 animate 屬性設為 false。
>將你的圖示放在 icon 屬性中，即可為這個元件設定 drawable 圖示。

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

######小型浮動按鈕（Float small button）

![float small button](images/float_small_button.png)

```xml
<com.gc.materialdesign.views.ButtonFloatSmall
                android:id="@+id/buttonFloatSmall"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:background="#1E88E5"
                materialdesign:iconDrawable="@drawable/ic_action_new" />
```

####開關

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

####進度指示器

######圓形不確定進度條
![progress bar circular indeterminate](images/progress_bar_circular_indeterminate.png)

```xml
<com.gc.materialdesign.views.ProgressBarCircularIndeterminate
                android:id="@+id/progressBarCircularIndeterminate"
                android:layout_width="32dp"
                android:layout_height="32dp"
                android:background="#1E88E5" />
```

######不確定進度條
![progress bar indeterminate](images/progress_bar_indeterminate.png)

```xml
<com.gc.materialdesign.views.ProgressBarIndeterminate
                android:id="@+id/progressBarIndeterminate"
                android:layout_width="fill_parent"
                android:layout_height="wrap_content"
                android:background="#1E88E5" />
```

######不確定／確定進度條
![Progress bar indeterminate determinate](images/progress_bar_indeterminate_determinate.png)


```xml
<com.gc.materialdesign.views.ProgressBarIndeterminateDeterminate
                android:id="@+id/progressBarIndeterminateDeterminate"
                android:layout_width="fill_parent"
                android:layout_height="wrap_content"
                android:background="#1E88E5" />
```

>如果你要開始顯示進度，只需要設定進度值即可
>
>```java
>progressBarIndeterminateDeterminate.setProgress(progress);
>```

######確定進度條
![Progress bar determinate](images/progress_bar_determinate.png)


```xml
<com.gc.materialdesign.views.ProgressBarDeterminate
                android:id="@+id/progressDeterminate"
                android:layout_width="fill_parent"
                android:layout_height="wrap_content"
                android:background="#1E88E5" />
```

>你可以使用 `materialdesign:max="50"` 和 `materialdesign:min="25"` 屬性自訂進度的最大值與最小值。

######滑桿（Slider）
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

######帶數字指示器的滑桿
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

##小工具

####SnackBar

![Snackbar](images/snackbar.png)


```java
SnackBar snackbar = new SnackBar(Activity activity, String text, String buttonText, View.OnClickListener onClickListener);
snackbar.show();
```

> 如果你不想顯示按鈕，請在 `buttonText` 屬性中傳入 `null`

####Dialog

![Dialog](images/dialog.png)

```java
Dialog dialog = new Dialog(Context context,String title, String message);
dialog.show();
```

>你可以在事件監聽器中設定確定與取消按鈕，或更改它們的文字
>```java
> // 設定確定按鈕的點擊監聽器
>dialog.setOnAcceptButtonClickListener(View.OnClickListener onAcceptButtonClickListener);
> // 設定取消按鈕的點擊監聽器
>dialog.setOnCancelButtonClickListener(View.OnClickListener onCancelButtonClickListener);
> // 存取確定按鈕
>ButtonFlat acceptButton = dialog.getButtonAccept();
> // 存取取消按鈕
>ButtonFlat cancelButton = dialog.getButtonCancel();
>```

####顏色選擇器

![Color selector](images/color_selector.png)

```java
ColorSelector colorSelector = new ColorSelector(Context context,int intialColor, OnColorSelectedListener onColorSelectedListener);
colorSelector.show();
```