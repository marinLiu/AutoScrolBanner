# AutoScrolBanner

##Getting Started

 - Add the dependency to your build.gradle.
 
```
dependencies {
    compile 'com.zhangjingjing:autoscrolbanner:1.0.1'
}
```
- Maven:

```
<dependency>
  <groupId>com.zhangjingjing</groupId>
  <artifactId>autoscrolbanner</artifactId>
  <version>1.0.1</version>
  <type>pom</type>
</dependency>
```

## Usage
- xml

```

    <com.zhangjingjing.autoscrolbanner.CycleViewpager
        android:id="@+id/vp_auto"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>

        <com.isanwenyu.tabview.TabView
            android:id="@+id/tab_chat"
            style="@style/TabView"
            app:imgDrawable="@drawable/tab_chat"
            app:imgDimension="@dimen/tab_img_size"
            app:imgMargin="@dimen/tab_img_margin"
            app:textColor="@color/tab_chat_text_selector"
            app:textSize="@dimen/tab_view_text_size"
            app:textString="聊天" />

     <com.zhangjingjing.autoscrolbanner.PagerIndicator
        android:id="@+id/pi_indicator"
        app:indicator_font_color="@color/colorAccent"
        app:indicator_font_size="12sp"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentBottom="true"
        android:layout_marginBottom="10dp"
        app:indicator_type="number"
        />
            
        .......
     
```

- code

```
 mTabGroup.setOnCheckedChangeListener(new TabGroup.OnCheckedChangeListener() {
            @Override
            public void onCheckedChanged(TabGroup group, int checkedId) {
                switch (checkedId) {
                    case R.id.tab_chat:
                        setCurrentFragment(TAB_CHAT);
                        break;
                    case R.id.tb_pic:
                        setCurrentFragment(TAB_PIC);
                        break;
                    case R.id.tb_app:
                        setCurrentFragment(TAB_APP);
                        break;
                    case R.id.tb_user:
                        setCurrentFragment(TAB_USER);
                        break;
                }
            }
        });

```
```
   mAutoVp = (CycleViewpager) findViewById(R.id.vp_auto);
        mIndicator = (PagerIndicator) findViewById(R.id.pi_indicator);
        MyPagerAdapter adapter = new MyPagerAdapter(this, imgUrls);
        mAutoVp.setAdapter(adapter);
        mAutoVp.startAutoScroll();
        mIndicator.setViewpager(mAutoVp);
```

## Todo

 ~~支持viewpager切换动画配置~~ <br>
 支持indicator切换动画配置
 优化

## License

    Copyright 2016 13663797524@163.com

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
