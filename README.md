# Lobsterpicker
Designed by <a href="http://dvsty.com">Marie Schweiz</a>, Developed by <a href="https://larswerkman.com">Lars Werkman</a>

Lobsterpicker is a library for android material design made to support apps and developers if a color should be choosen by a user. The library is offering a dialog with all shades of material design colors. Give it a try via google play

## How you can use it:

Include one or multiple of the views inside of you layout:
```xml
<com.larswerkman.lobsterpicker.LobsterPicker
    android:id="@+id/lobsterpicker"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content" />

<com.larswerkman.lobsterpicker.sliders.LobsterShadeSlider
    android:id="@+id/shadeslider"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content" />

<com.larswerkman.lobsterpicker.sliders.LobsterOpacitySlider
    android:id="@+id/alphaslider"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content" />
```


## summary of options

* color wheel you prefer (wheel only)
* color wheel and a before and after circle in the middle
* color wheel and a slider/toggle for switching between different color spaces
* color wheel, a slider/toggle for the colorspace and the opacity
* slider only, toggle for shades of one colors only
* slider only,  toggle for 5 different shades you define


#### color wheel you prefer (wheel only)

<p style="display: table-cell; align-vertical: middle">
<img style="vertical-align: middle;" src="http://dvsty.com/git-lobsterpicker/option-wheel.png">
<span>
```java
LobsterPicker lobsterPicker = (LobsterPicker) findViewById(R.id.lobsterpicker);

//To retrieve to color use
lobsterPicker.getColor();

//You'r also able to add on listener
lobsterPicker.addOnColorListener(new OnColorListener() {
    @Override
    public void onColorChanged(@ColorInt int color) {
        
    }

    @Override
    public void onColorSelected(@ColorInt int color) {

    }
});
```
</span>
</p>

#### color wheel and a before and after circle in the middle

![image](http://dvsty.com/git-lobsterpicker/option-wheel-circle.png)
how to use:

#### color wheel and a slider/toggle for switching between different color spaces

![image](http://dvsty.com/git-lobsterpicker/option-wheel-toggle-opacity.png)
how to use:

#### color wheel, a slider/toggle for the colorspace and the opacity

![image](http://dvsty.com/git-lobsterpicker/option-wheel-toggle-opacity.png)
how to use:

#### slider only, toggle for shades of one colors only

![image]()
how to use:

#### slider only,  toggle for 5 different shades you define

![image](http://dvsty.com/git-lobsterpicker/option-toggle.png)
how to use:


## Download
Maven:
```xml
<dependency>
	<groupId>com.larswerkman</groupId>
	<artifactId>lobsterpicker</artifactId>
	<version>1.0.0</version>
</dependency>
```

Gradle:
```groovy
compile 'com.larswerkman:lobsterpicker:1.0.0'
``` 


## License
```license
Copyright (C) 2015 Marie Schweiz & Lars Werkman
Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at
    http://www.apache.org/licenses/LICENSE-2.0
Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```


## Credits
This library is written and developed by <a href="https://larswerkman.com">Lars Werkman</a>. For feedback, requests and collaboration please use Github or write us. 

Lars Werkman
Freelance android developer
werkman.lars@gmail.com

Marie Schweiz
Freelance android designer
marie.schweiz@gmail.com