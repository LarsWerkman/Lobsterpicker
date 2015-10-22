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
    android:id="@+id/opacityslider"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content" />
```


## summary of options

* color wheel you prefer (wheel only)
* color wheel and a before and after circle in the middle
* color wheel and a slider for switching between different color spaces
* color wheel, a slider for the colorspace and the opacity
* slider only, toggle for 5 different shades you define
* slider only and opacity

#### color wheel you prefer (wheel only)

![image](http://dvsty.com/git-lobsterpicker/option-wheel.png)

```java
LobsterPicker lobsterPicker = (LobsterPicker) findViewById(R.id.lobsterpicker);

//To retrieve the selected color use
lobsterPicker.getColor();

//You'r also able to add a listener
lobsterPicker.addOnColorListener(new OnColorListener() {
    @Override
    public void onColorChanged(@ColorInt int color) {
        
    }

    @Override
    public void onColorSelected(@ColorInt int color) {

    }
});
```

#### color wheel and a before and after circle in the middle

![image](http://dvsty.com/git-lobsterpicker/option-wheel-circle.png)

By default this is disabled your able to enable it in xml

```xml
app:color_history_enabled="true"
```

Or in Java

```java
LobsterPicker lobsterPicker = (LobsterPicker) findViewById(R.id.lobsterpicker);

//To enable to color feedback use
lobsterPicker.setColorHistoryEnabled(true);

//To set a previous picked color or reference color use
lobsterPicker.setHistory(Color.RED);
```

#### color wheel and a slider for switching between different color spaces

![image](http://dvsty.com/git-lobsterpicker/option-wheel-toggle.png)

To connect a slider to the color wheel use

```java
LobsterPicker lobsterPicker = (LobsterPicker) findViewById(R.id.lobsterpicker);
LobsterShadeSlider shadeSlider = (LobsterShadeSlider) findViewById(R.id.shadeslider);

//To connect them
lobsterpicker.addDecorator(shadeSlider);
```

All sliders implement the `ColorDecorator` interface, which enables them to manipulate the user selected color.
Important to notice is the sequence you add decorators, because the first decorator that is added will be the first to manipulate the color.

#### color wheel, a slider for the colorspace and the opacity

![image](http://dvsty.com/git-lobsterpicker/option-wheel-toggle-opacity.png)

To connect both the `LobsterShadeSlider` and `LobsterOpacitySlider` isn't any diffent then the previous mentioned method

```java
LobsterPicker lobsterPicker = (LobsterPicker) findViewById(R.id.lobsterpicker);
LobsterShadeSlider shadeSlider = (LobsterShadeSlider) findViewById(R.id.shadeslider);
LobsterOpacitySlider opacitySlider = (LobsterOpacitySlider) findViewById(R.id.opacityslider);

//To connect them
lobsterpicker.addDecorator(shadeSlider);
lobsterpicker.addDecorator(opacitySlider);
```

#### slider only, toggle for 5 different shades you define

![image](http://dvsty.com/git-lobsterpicker/option-toggle.png)

The `LobsterShadeSlider` can also be used as a standalone color selector.

```java
//To retrieve to color is the same mehtod used for the LobsterPicker
shadeSlider.getColor();
```

To use your own colors this can be done by implementing the `ColorAdapter` interface.
Or use the existing `BitmapColorAdapter` which takes a Drawable as color source.

```java
lobsterPicker.setColorAdapter(new BitmapColorAdapter(this, R.drawable.default_shader_pallete));
```

#### slider only and opacity

![image](http://dvsty.com/git-lobsterpicker/option-toggle-opacity.png)

Just like for the `LobsterPicker` you have to add the opacity slider as a decorator
```java
LobsterShadeSlider shadeSlider = (LobsterShadeSlider) findViewById(R.id.shadeslider);
LobsterOpacitySlider opacitySlider = (LobsterOpacitySlider) findViewById(R.id.opacityslider);

//To connect them
shadeSlider.addDecorator(opacitySlider);
```


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