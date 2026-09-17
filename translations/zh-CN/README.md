![Material design library logo](images/logo.png)

<!-- github-global:langs:start -->
[简体中文](./README.md) | [繁體中文](../zh-TW/README.md) | [日本語](../ja/README.md)
<!-- github-global:langs:end -->


# Material Design Android Library

<a href="https://play.google.com/store/apps/details?id=com.gc.demomaterialdesign">
  <img alt="Android app on Google Play" src="https://developer.android.com/images/brand/en_app_rgb_wo_45.png" />
</a>


[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-Material%20Design%20Android%20Library-brightgreen.svg?style=flat)](https://android-arsenal.com/details/1/1156)

* [如何使用](#howtouse)
* [组件](#components)
    * [按钮](#buttons)
        * [扁平按钮（Flat Button）](#flat-button)
        * [矩形按钮（Rectangle Button）](#rectangle-button)
        * [浮动按钮（Float Button）](#float-button)
        * [小型浮动按钮（Float small button）](#float-small-button)
    * [开关](#switches)
        * [复选框（CheckBox）](#checkbox)
        * [开关（Switch）](#switch)
    * [进度指示器](#progress-indicators)
        * [圆形不确定进度条](#progress-bar-circula-rindeterminate)
        * [不确定进度条](#progress-bar-indeterminate)
        * [不确定/确定进度条](#progress-bar-indeterminate-determinate)
        * [确定进度条](#progress-bar-determinate)
        * [滑块（Slider）](#slider)
        * [带数字指示器的滑块](#slider-with-number-indicator)
* [小部件](#widgets)
    * [SnackBar](#snackbar)
    * [对话框（Dialog）](#dialog)
    * [颜色选择器（Color selector）](#color-selector)

## 如何使用

如果你想使用这个库，只需下载 MaterialDesign 项目，将其导入你的工作区，并在你的 Android 项目设置中把该项目添加为库。

如果你愿意，也可以使用 gradle 依赖，只需在 build.gradle 文件中添加以下几行：

```xml
repositories {
    jcenter()
}

dependencies {
    compile 'com.github.navasmdc:MaterialDesign:1.+@aar'
}
```

某些组件具有自定义属性，如果你想使用它们，必须在 xml 文件的第一个组件中添加这一行：

```xml
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:materialdesign="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    >
</RelativeLayout>
```

>如果你打算使用 ScrollView，建议使用本库提供的 CustomScrollView，以避免自定义组件出现问题。
>使用该组件的方法：
>```xml
><com.gc.materialdesign.views.ScrollView 
>    xmlns:android="http://schemas.android.com/apk/res/android"
>    xmlns:materialdesign="http://schemas.android.com/apk/res-auto"
>    android:id="@+id/scroll"
>    android:layout_width="match_parent"
>    android:layout_height="match_parent">
></com.gc.materialdesign.views.ScrollView>
>```

##组件

####按钮

######扁平按钮（Flat Button）

![flat button](images/flat_button.png)
```xml
<com.gc.materialdesign.views.ButtonFlat
                android:id="@+id/buttonflat"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:background="#1E88E5"
                android:text="Button" />
```

######矩形按钮（Rectangle Button）

![rectangle button](images/rectangle_button.png)
```xml
<com.gc.materialdesign.views.ButtonRectangle
                android:id="@+id/button"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:background="#1E88E5"
                android:text="Button" />
```

######浮动按钮（Float Button）

![float button](images/float_button.png)

>建议将此组件放置在屏幕右下角。要使用此组件，请在你的 xml 文件中写入以下代码。
>如果你不想让此组件以动画方式启动，请将 animate 属性设置为 false。
>将你的图标放在 icon 属性中，即可为该组件设置 drawable 图标。

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

######小型浮动按钮（Float small button）

![float small button](images/float_small_button.png)

```xml
<com.gc.materialdesign.views.ButtonFloatSmall
                android:id="@+id/buttonFloatSmall"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:background="#1E88E5"
                materialdesign:iconDrawable="@drawable/ic_action_new" />
```

####开关

######复选框（CheckBox）
![checkbox](images/checkbox.png)

```xml
<com.gc.materialdesign.views.CheckBox
                android:id="@+id/checkBox"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:background="#1E88E5"
                materialdesign:check="true" />
```

######开关（Switch）
![switch](images/switch.png)

```xml
<com.gc.materialdesign.views.Switch
                android:id="@+id/switchView"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:background="#1E88E5"
                materialdesign:check="true" />
```

####进度指示器

######圆形不确定进度条
![progress bar circular indeterminate](images/progress_bar_circular_indeterminate.png)

```xml
<com.gc.materialdesign.views.ProgressBarCircularIndeterminate
                android:id="@+id/progressBarCircularIndeterminate"
                android:layout_width="32dp"
                android:layout_height="32dp"
                android:background="#1E88E5" />
```

######不确定进度条
![progress bar indeterminate](images/progress_bar_indeterminate.png)

```xml
<com.gc.materialdesign.views.ProgressBarIndeterminate
                android:id="@+id/progressBarIndeterminate"
                android:layout_width="fill_parent"
                android:layout_height="wrap_content"
                android:background="#1E88E5" />
```

######不确定/确定进度条
![Progress bar indeterminate determinate](images/progress_bar_indeterminate_determinate.png)


```xml
<com.gc.materialdesign.views.ProgressBarIndeterminateDeterminate
                android:id="@+id/progressBarIndeterminateDeterminate"
                android:layout_width="fill_parent"
                android:layout_height="wrap_content"
                android:background="#1E88E5" />
```

>如果你要开始显示进度，只需设置进度值即可
>
>```java
>progressBarIndeterminateDeterminate.setProgress(progress);
>```

######确定进度条
![Progress bar determinate](images/progress_bar_determinate.png)


```xml
<com.gc.materialdesign.views.ProgressBarDeterminate
                android:id="@+id/progressDeterminate"
                android:layout_width="fill_parent"
                android:layout_height="wrap_content"
                android:background="#1E88E5" />
```

>你可以使用 `materialdesign:max="50"` 和 `materialdesign:min="25"` 属性来自定义进度的最大值和最小值。

######滑块（Slider）
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

######带数字指示器的滑块
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

##小部件

####SnackBar

![Snackbar](images/snackbar.png)


```java
SnackBar snackbar = new SnackBar(Activity activity, String text, String buttonText, View.OnClickListener onClickListener);
snackbar.show();
```

>如果你不想显示按钮，请在 `buttonText` 属性中传入 `null`

####对话框（Dialog）

![Dialog](images/dialog.png)

```java
Dialog dialog = new Dialog(Context context,String title, String message);
dialog.show();
```

>你可以在事件监听器中设置确认和取消按钮，或者修改它们的文本
>```java
> // 设置确认按钮点击监听器
>dialog.setOnAcceptButtonClickListener(View.OnClickListener onAcceptButtonClickListener);
> // 设置取消按钮点击监听器
>dialog.setOnCancelButtonClickListener(View.OnClickListener onCancelButtonClickListener);
> // 获取确认按钮
>ButtonFlat acceptButton = dialog.getButtonAccept();
> // 获取取消按钮
>ButtonFlat cancelButton = dialog.getButtonCancel();
>```

####颜色选择器（Color selector）

![Color selector](images/color_selector.png)

```java
ColorSelector colorSelector = new ColorSelector(Context context,int intialColor, OnColorSelectedListener onColorSelectedListener);
colorSelector.show();
```