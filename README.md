# XRApp

Project-S 是 **世界首个 visionOS 模拟器应用商店** ，它将允许你将自己开发的 visionOS 应用分发给来自世界各地的尝鲜者们。
<br>
本仓库是 Project-S 的应用检索仓库。如果你想在 Project-S 上 **发布，分发，或是更新** 已有应用，你需要在本仓库提交相关元信息文件。
<br>
注意，你无需在本仓库上传应用本体，此外 Project-S 没有强制你必须开源你的应用，你只需要上传基本的元信息就可以开始分发你的应用。

## 发布新 App

### 基本结构

每个需要在 Project-S 上发布的应用，都需要在本仓库下的 `XRApps` 中创建一个文件夹，并在文件夹中包含相关文件。为了防止文件夹名称重复，我们建议你将其命名为具有唯一性质的名字，如 Bundle ID。
<br>
下面是文件夹的基本结构：

```other
Folder
  - meta.json
  - info.json
  - some_icon.png
  - some_photo.png
```

### meta.json

`meta.json` 用来储存一些基本元信息，主要被用来标识应用和检索使用。
<br>
下面是一个示例文件：

```json
{
    "id": "579271a6-b86a-4dae-bbed-f856e830b42d",
    "name": "HelloWorld",
    "featuredImage": "helloworld-feature.png",
    "icon": "icon.png",
    "version": "1.0.0",
    "repo": "https://github.com/XRealityZone/what-vision-os-can-do",
    "slogan": "Meet the visionOS",
    "category": "Developer",
    "bundle": "zone.xreality.WhatVisionOSCanDo"
}
```

以下是对于各字段用法的解释：

| 字段名称          | 是否必要 | 用途                                       |
| ------------- | ---- | ---------------------------------------- |
| id            | 必要   | 应用标识，为UUID字符串，需自行生成，不能重复                 |
| name          | 必要   | 应用名称                                     |
| featuredImage | 非必要  | 应用精选图片，推荐大小为 1300*800，如不添加，应用将不会在首页精选区展示 |
| slogan        | 非必要  | 应用标语，如果填写了 `featuredImage` 则必须填写该字段      |
| icon          | 必要   | 应用图标，推荐大小为512*512，自动裁切为圆形                |
| version       | 必要   | 应用当前版本，支持 x.x 和 x.x.x 格式                 |
| repo          | 必要   | 应用的 GitHub Repo 地址，用于下载应用，该 Repo 无需包含代码  |
| category      | 必要   | 应用分类，分类目录见下表                             |
| bundle        | 必要   | 应用的 bundle id                            |

## info.json

`info.json` 用来储存应用基本内容信息，将会被渲染并展示于应用详情页面。
<br>
下面是一个示例文件：

```json
{
    "author": "Ryan Zhu",
    "description": "Unlock the full potential of your vision with EyeSight, a groundbreaking vision OS app designed to enhance and manage your visual experiences in real-time. EyeSight leverages the most advanced artificial intelligence and machine learning algorithms to analyze and interpret visual data, providing you with a host of functionalities that will redefine the way you see the world.\nKey Features:\nEnhanced Visual Perception: EyeSight uses real-time image processing and computer vision algorithms to optimize the images and videos you see, adjusting contrast, brightness, and sharpness to provide a clearer, more detailed view of your surroundings.\nObject and Text Recognition: EyeSight can identify and categorize objects and text in your field of vision, providing you with relevant information and context about what you are looking at.",
    "developerWebsite": "https://apple.com",
    "images": ["1.png", "2.png", "3.png"]
}
```

以下是对于各字段用法的解释：

| 字段名称             | 是否必要 | 解释           |
| ---------------- | ---- | ------------ |
| author           | 必要   | 应用开发者名称      |
| description      | 必要   | 应用简介，可使用转义字符 |
| developerWebsite | 必要   | 开发者网站        |
| images           | 必要   | 应用截图         |

### 关于图片

在 `meta.json` 和 `info.json` 中有大量字段需要填写图片地址，目前还不支持填写图片链接，需要将所有图片存到文件夹中，并在 JSON 文件中使用相对路径调用。

### 应用本体

在 `meta.json` 的 `repo` 字段中，你需要填写应用本体所在的公开仓库。当你提交你的第一个应用的时候，请先创建一个 release，并将你的应用程序（ `.app` 结尾文件）打包为 `app.zip` 上传至该 release，并发布。Project-S 将会通过 `meta.json` 查询你的 latest release，并下载应用。

