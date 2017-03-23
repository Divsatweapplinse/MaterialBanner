# MaterialBanner

Support API Level 8+

## ScreenShot:
![](https://github.com/joielechong/MaterialBanner/blob/master/screenshot/GIF.gif)


## Idea from Google Trips:
![](https://github.com/joielechong/MaterialBanner/blob/master/screenshot/googletrips.jpg)


##[Demo APK](https://github.com/joielechong/MaterialBanner/releases/download/1.0.0/Demo.apk)

### Attrs
|attr|format|default|
|---|---|---|
|indicatorMargin|dimension|10dp|
|indicatorInside|boolean|true|
|indicatorGravity|flag:left,center,right|left|
|match|boolean|false|


### Gradle:

Step 1. Add the JitPack repository in your root build.gradle at the end of repositories:
```
 allprojects {
      repositories {
          ...
          maven { url "https://jitpack.io" }
      }
}
```
Step 2. Add the dependency
```
compile 'com.github.joielechong:materialbanner:1.0.0'
```

XML
```xml
  <com.freegeek.android.materialbanner.MaterialBanner
      android:id="@+id/material_banner"
      android:layout_width="match_parent"
      app:match="true"
      android:layout_height="200dp"/>
```

```java
  MaterialBanner materialBanner = (MaterialBanner) findViewById(R.id.material_banner);
  materialBanner.setPages(new ViewHolderCreator() {
            @Override
            public Object createHolder() {
                return new ImageHolderView();
            }
        },bannerData);
  //set circle indicator
  materialBanner.setIndicator(new CirclePageIndicator(this));
  //indicators:
  //CirclePageIndicator,IconPageIndicator,LinePageIndicator
  //Custom indicator view needs to implement com.freegeek.android.materialbanner.view.indicator.PageIndicator
  
```
[More usage](https://github.com/joielechong/MaterialBanner/blob/master/app/src/main/java/com/freegeek/android/materialbanner/demo/MainActivity.java)

Listener
```java
  
  materialBanner.setOnItemClickListener(new MaterialBanner.OnItemClickListener() {
            @Override
            public void onItemClick(int position) {
                
            }
        });
  
  materialBanner.setOnPageChangeListener(new ViewPager.OnPageChangeListener() {
            @Override
            public void onPageScrolled(int position, float positionOffset, int positionOffsetPixels) {

            }

            @Override
            public void onPageSelected(int position) {
                textView.setText("My hometown: page " + ++position);
            }

            @Override
            public void onPageScrollStateChanged(int state) {

            }
        });
        
        
```

## Thanks to:
[Android-ConvenientBanner](https://github.com/saiwu-bigkoo/Android-ConvenientBanner)	
[ViewPagerIndicator](https://github.com/JakeWharton/ViewPagerIndicator)

## License

Copyright (C) 2017 Joielechong.
Copyright (C) 2004 Leon Fu <rtugeek@gmail.com>

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
