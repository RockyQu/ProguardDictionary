# ProguardDictionary
混淆配置与字典文件

## Usage
把 proguard-dictionary.txt 文件放到 App Module 根目录下，将下面参数加入到 proguard-rules.pro 里
```
# 指定一个文本文件用来生成混淆后的名字。默认情况下，混淆后的名字一般为 a、b、c 这种。
# 通过使用配置的字典文件，可以使用一些非英文字符做为类名。成员变量名、方法名。字典文件中的空格，标点符号，重复的词，还有以'#'开头的行都会被忽略。
# 需要注意的是添加了字典并不会显著提高混淆的效果，只不过是更不利与人类的阅读。正常的编译器会自动处理他们，并且输出出来的jar包也可以轻易的换个字典再重新混淆一次。
# 最有用的做法一般是选择已经在类文件中存在的字符串做字典，这样可以稍微压缩包的体积。
# 查找了字典文件的格式：一行一个单词，空行忽略，重复忽略
-obfuscationdictionary proguard-dictionary.txt

# 指定一个混淆类名的字典，字典格式与 -obfuscationdictionary 相同
-classobfuscationdictionary proguard-dictionary.txt
# 指定一个混淆包名的字典，字典格式与 -obfuscationdictionary 相同
-packageobfuscationdictionary proguard-dictionary.txt
```

## Analyze APK
打包好的 APK 使用 Android Studio 的 Analyze APK 能够看到混淆后的结果
![](https://github.com/RockyQu/ProguardDictionary/blob/master/ImageFolder/proguard1.png "")

## Dictionary Rules
字典规则：一行一个单词，空行忽略，重复忽略  
你可以修改文件添加你自己的字典规则，甚至可以添加中文，随便怎么玩(゜- ゜)つロ
