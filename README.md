# NotePad 项目

## 项目简介

这个项目是一个基于NotePad应用基础上进行二次开发的简单的笔记应用，支持笔记管理、搜索和排序功能。用户可以在主页上按标题或最后修改时间对笔记进行排序，并在笔记内部自定义背景颜色。每个笔记会显示最后修改的时间戳，方便用户查看修改记录。

## 功能特点

### 基础功能：
#### 时间戳显示：每个笔记会显示最后修改的时间戳。
![Alt Text](./README_PIC/A009.png)

#### 主页搜索：用户可以通过笔记标题搜索笔记。
![Alt Text](./README_PIC/A001.png) ![Alt Text](./README_PIC/A002.png) ![Alt Text](./README_PIC/A003.png) ![Alt Text](./README_PIC/A004.png)

### 附加功能：
#### 排序功能：默认按照最后修改时间排序，点击排序按钮后按照笔记标题首字母排序（包括字母、汉字、数字和标点符号的排序）。
![Alt Text](./README_PIC/A005.png) ![Alt Text](./README_PIC/A006.png)

#### 更换背景：在笔记编辑页面，可以设置笔记的背景颜色。
![Alt Text](./README_PIC/A007.png) ![Alt Text](./README_PIC/A011.png) ![Alt Text](./README_PIC/A008.png) ![Alt Text](./README_PIC/A010.png) 

## 安装与使用

1. 将项目克隆到本地：
    ```bash
    git clone https://github.com/amsatorian/Android_SemiExpt.git
    ```

2. 导入 Android Studio 并构建项目。

3. 运行应用程序并开始使用。

## 项目主要结构

### Java类

#### NoteEditor.java:
笔记编辑页面的 Activity，负责笔记的编辑和保存功能<br>
#### NotePad.java:
主 Activity，负责展示笔记列表和其他功能，如排序、搜索等<br>
#### NotePadProvider.java:
提供数据库访问和内容提供者功能，用于与数据库交互<br>
#### NotesList.java:
笔记列表的 Activity，展示所有笔记的列表<br>
#### NotesLiveFolder.java:
处理与文件夹和笔记的动态管理功能<br>
#### TitleEditor.java:
负责编辑笔记标题的 Activity<br>

### Layout布局文件

#### note_editor.xml:
笔记编辑页面的布局文件，包含编辑框、按钮等<br>
#### noteslist_item.xml:
单个笔记项的布局文件，展示笔记标题和其他信息<br>
#### title_editor.xml:
标题编辑页面的布局文件，用于编辑笔记的标题<br>

## 配置详情

### 1. `使用JDK9的版本`

### 2. `gradle-wrapper.properties`

请使用以下配置的 `distributionUrl`：

![Alt Text](./001.png)

```properties
distributionUrl=https\://services.gradle.org/distributions/gradle-6.7.1-bin.zip
```

### 3.  `build.gradle(notepad)`
classpath请使用3.4.0:

![Alt Text](./002.png)

```properties
classpath="com.android.tools.build:gradle:3.4.0"
```
### 4. `build成功之后`
#### 4.1 `Error:Execution failed for task ':app:packageDebug'... 出现这个报错`
build.gradle（:app）中的 android{ ... } 中 添加：

![Alt Text](./003.png)

```properties
packagingOptions {
    exclude 'META-INF/DEPENDENCIES.txt'
    exclude 'META-INF/LICENSE.txt'
    exclude 'META-INF/NOTICE.txt'
    exclude 'META-INF/NOTICE'
    exclude 'META-INF/LICENSE'
    exclude 'META-INF/DEPENDENCIES'
    exclude 'META-INF/notice.txt'
    exclude 'META-INF/license.txt'
    exclude 'META-INF/dependencies.txt'
    exclude 'META-INF/LGPL2.1'
}
```
#### 4.2 `com.android.ide.common.signing.KeytoolException: Failed to read key AndroidDebugKey from store出现这个问题`
请删除以下两个文件并clean build之后rebuild（此文件的地址请看报错信息）:

![Alt Text](./004.png)

## 贡献者

Amsatorian：项目的拓展功能贡献者。
