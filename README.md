Android 二进制AndroidManifest.xml 文件解析器，提供了很弱的编辑功能，我用来编辑友盟的渠道。


///////////////////////修改的内容
将xml文件中所有value为{CHANNEL}的值全部替换为输入的渠道号，而不只是替换友盟UMENG_CHANNEL的渠道号

1. 用法与之前一致，配合[友盟渠道打包工具](https://github.com/umeng/umeng-muti-channel-build-tool)使用
2. 基础的apk需要在AndroidManifest.xml文件中配置需要修改的meta-data的value为{CHANNEL}


示例：
AndroidManifest.xml中的如下配置：

        <meta-data
            android:name="UMENG_CHANNEL"
            android:value="{CHANNEL}"/>
        <meta-data
            android:name="JPUSH_CHANNEL"
            android:value="{CHANNEL}"/>
        <meta-data
            android:name="FOO_CHANNEL"
            android:value="{CHANNEL}"/>

假设在打包工具中指定渠道为hello，则以上配置将会被替换为如下内容：

        <meta-data
            android:name="UMENG_CHANNEL"
            android:value="hello"/>
        <meta-data
            android:name="JPUSH_CHANNEL"
            android:value="hello"/>
        <meta-data
            android:name="FOO_CHANNEL"
            android:value="hello"/>
