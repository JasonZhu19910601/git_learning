# config.gradle

1.项目依赖版本

2.v4 v7包版本

3.项目版本配置

4.ip地址配置

# 环境配置

配置内容包含：app名称，app包名，ip地址

当前环境包含三种，如需添加可另行在config.gradle中添加

正式 app名称：哈尔滨银行  包名：com.yitong.hrb.people.android

**app名称和包名不可更改，否则密码键盘初始化有误，获取密码为空**

```java
huidu {
    dimension "environment"
    applicationIdSuffix ".huidu"
    manifestPlaceholders = [
            PACKAGE_NAME    : "com.yitong.hrb.people.android",
            APP_NAME        : "哈行-灰度",
            GETUI_APP_ID    : "ew9M1qG6oI9tpLgdfhbpI9",
            GETUI_APP_KEY   : "6o6TC1vX4s8zx1QGtcnKd3",
            GETUI_APP_SECRET: "lhmXJk7onT7DcpoZS3KkwindowIsFloatingf1",
            MEIZU_APP_ID    : "110832",
            MEIZU_APP_KEY   : "2936447b92b14b92abd17a095fd3e192",
            HUAWEI_APP_ID   : "100039781",
            XIAOMI_APP_ID   : "2882303761517594658",
            XIAOMI_APP_KEY  : "5891759455658"
    ]
    buildConfigField "String", "API_HOST", "${rootProject.ext.flavor.API_HUIDU}"
}
```

## 环境切换

在hRB_PEOPLE build.gradle中productFlavor配置

![](.README_images/a448b0f8.png)





##### Log开关，由BuildConfig控制，BuildConfig的生成与第一步的环境切换相关

# Apk打包

一键打包
1.打开as右侧 Gradle

2.HarbinApp下的build目录

3.双击选择打包环境 可打出相关apk

![](.README_images/51f94e66.png)

    assembleZhengshi assembleHuidu  assembleCeshi --可打出 debug release包
    assembleDebug 可打出所有渠道debug包
    assembleRelease 可打出所有渠道release包
4.输出目录：项目根目录下 apk目录
5.apk输出形式：Harbinbank_ceshi_debug_1.0.0_20190909.apk

----------------------------------------------------------------xianmei.li编辑于2019.7.17


为了避免NatviePlugin.java文件太过臃肿
1.与H5数据交互时，解析方式通过StringUtils.jsonToClass()解析获取数据JavaBean，减少try catch代码
2.相关dialog弹出，尽量写进DialogManage.java，避免函数所占代码行数过多，尽量限制在30行左右，或将函数迁移至DialogPlugin.java文件中
3.除JS所需函数，尽量避免将自定义方法写进NativePlugin.java文件中。
4.注释代码如非必要，尽快删除，若需备份，另行创建.java文件
5.业务类型单一，非公共函数所需的JS函数，另行创建Plugin文件，继承BasePlugin，交互名称格式：XXXJs
6.删除调试所加的Log代码
注：现有代码，如有时间麻烦各位同学进行修改下~
----------------------------------------------------------------xianmei.li编辑于2019.8.5
OCR相关
业务
OCRUtils.java
1.银行卡识别
2.证件识别
4.人脸识别
----------------------------------------------------------------xianmei.li编辑于2019.8.5

PassGuardEdit键盘种类配置  
配置方法 :setReorder(int type)
配置参数：
KEY_NONE_CHAOS    不乱序且不带气泡和点击效果
KEY_CHAOS_SWITCH_VIEW  乱序切不带气泡和点击效果
KEY_CHAOS_PRESS_KEY   不乱序不带气泡和点击效果
----------------------------------------------------------------xianmei.li编辑于2019.8.11
需求编号：my_mon_201909_YWXQ20190815100611
修改内容：声纹登录
厂商开发：董彬彬
----------------------------------------------------------------tengfei.li编辑于2019.10.24
esscsdk_v2.0.6.aar 电子社保卡
PALiveDetect4.4.3.aar
libface_detect.so armeabi_v7a
----------------------------------------------------------------xianmei.li编辑于2020.7.27
ytBasicFramework中增加FileConfig.java文件（文件配置都在此类种，适配android11分区存储）
Environment.getExternalStorageDirectory（）此类方法将不在支持，在android11中会无法正常读写文件
----------------------------------------------------------------zhi.li编辑于2020.01.25

cupdkeyboardlib.aar     -----电子信用卡

----------------------------------------------------------------zhi.li编辑于2020.01.25
3in1-online-v1.0.9.20210721-NL.aar  云从活体人脸识别ocr

----------------------------------------------------------------xianmei.li编辑于2021.08.11



