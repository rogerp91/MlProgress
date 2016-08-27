# MlProgress
https://jitpack.io

Add it to your build.gradle with:
```gradle
allprojects {
    repositories {
        maven { url "https://jitpack.io" }
    }
}
```
and:

```gradle
dependencies {
    compile 'com.github.rogerp91:MlProgress:{latest version}'
}
```

## Usage

You can create your own progress wheel in xml like this (remeber to add ```xmlns:wheel="http://schemas.android.com/apk/res-auto"```):

```xml
    <com.github.roger91.mlprogress.MlProgress
        android:id="@+id/progress_wheel"
        android:layout_width="80dp"
        android:layout_height="80dp"
        android:layout_centerHorizontal="true"
        wheel:rpProg_barColor="#5588FF"
        wheel:rpProg_progressIndeterminate="true" />
```
Or in code:

```Java
MlProgress mlProgress = new MlProgress(context);
mlProgress.setBarColor(Color.BLUE);
...

```

### Callback

Use ```setCallback(ProgressCallback)``` to assign a callback that will be called each time the progress changes. This way you can update a value on the progress alongside with the progress animation, or execute an action once the progress reaches a certain value. in the indeterminatge wheel, the callback is called with a value of -1.0f every time the animation cycle finishes (when the wheel shrinks back to its smaller size).

### Indeterminate wheel

For making the wheel indeterminate, just call the ```spin()``` method. If you set a progress value, the wheel will stop spinning.

You have two methods for setting the progress:

```mlProgress.setProgress(float value)```

Sets the value, and the wheel will smoothly animate to that value. The speed of the animation is defined by the spinSpeed (can be set with ```setSpinSpeed```, which number is the number of full turns per second)

```mlProgress.setInstantProgress(float value)```

Sets the value, and the wheel will instantly move to that value.

You can change other wheel properties such as the progress bar color, the wheel's background or the wheel's size and width.

### Fill radius

In case you want the spinning wheel to fill the whole layout instead of having a fixed size, you can use ```rpProg_fillRadius```.

### Based
  - [Material-ish Progress](https://github.com/pnikosis/materialish-progress)

### License
    Copyright 2016 Roger Patiño
    
    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0
    
    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
