# 应用提交指南

> * 如果你对英文比较熟悉，请阅读[英文版本](https://github.com/XRealityZone/XRApps/blob/main/README.md)的相关说明
> * 如果你对中文比较熟悉，请阅读[中文版本](https://github.com/XRealityZone/XRApps/blob/main/README_CN.md)的相关说明
> * 如果你对日文比较熟悉，请阅读[日文版本](https://github.com/XRealityZone/XRApps/blob/main/README_JP.md)的相关说明

## 欢迎你的加入

Apple Vision Pro 发布预示着空间计算时代的到来，让科技爱好者和开发者开始思考如何在新的交互、系统和硬件上打造独特的三维应用。

自 WWDC 2023 的发布会后，社交媒体上涌现了许多精美的 visionOS App 的效果图和演示视频，然而，由于 Apple Vision Pro 还未正式发布，所以我们很难试玩到其他开发者的作品。

为了解决这个问题，我们开发了 Let’s xrOS 这个 App，通过它，你可以试玩到社区里其他创作者的 visionOS App，抢先一步体验空间计算设备的魅力。

我们希望通过这个工具，能让开发者之间的交流更加频繁，并促进整个社区的发展。

Let’s xrOS 是一个 visionOS 应用交流平台 ，它将允许你将自己开发的 visionOS 应用分发给来自世界各地的尝鲜者们。
 
> Tip 1: **注意，你无需在本仓库上传应用本体，此外 Let’s xrOS  没有强制你必须开源你的应用，你只需要上传基本的元信息就可以开始分发你的应用。**
> 
> Tip 2: 这里是 Let’s xrOS 的应用检索仓库。如果你想在 Let’s xrOS 上 **发布或是更新** 自己的应用，你需要在本仓库提交相关元信息文件。
> 
> Tip 3: 如果你想下载 Let's xrOS 应用，你可以在[这个仓库](https://github.com/XRealityZone/Let-us-xrOS)的 release 页面下载并安装它，通过这个应用你可以把玩其他开发者创作的 visionOS 应用。

## 在 GitHub 上发布你的产品

- 运行你的项目，找到当前应用在 visionOS 模拟器下的二进制文件，将其压缩成 ZIP 包，保证其名称为 `app.zip` ，注意压缩包的名称不能更换，否则会导致检索应用信息失败(如果你不知道如何操作，可以查看 [FAQ 的第一个问题](https://github.com/XRealityZone/XRApps/blob/main/README_CN.md#faq))

<p align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/1faeadfa-2fca-4016-80b5-710622c3a55d" width="50%" height="50%">
</p>


- 在 GitHub 上创建当前应用的仓库（如果已经创建过，则跳过该步骤）。注意，请保证仓库类型是 `Public` 类型，否则会导致应用信息检索失败

<p align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/1e6d4e10-9bbf-4951-a832-e54b9cad488a" width="50%" height="50%">
</p>

- 进入该仓库的 `Release` 界面，选择需要发布的 tag 号，并上传压缩包，即之前准备的`app.zip` ，填写相应的 Release 版本名称（推荐此名称与 tag 号保持相同）。

<p align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/274944f9-dc0f-4c39-b008-1d9e4135663c" width="50%" height="50%">
</p>


## 提交你的 App 信息到 XReality.Zone 的信息源中

- 对 XReality.Zone 的 [XRApps 仓库](https://github.com/XRealityZone/XRApps) 进行 Fork 操作。

<p align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/12e7e8a5-05b3-404b-9416-711638511e0d" width="50%" height="50%">
</p>

- 克隆 Fork 后的仓库到本地并创建新的分支，分支的命名规则为 `app/Your_App’s_Bundle_ID`

<p align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/404f8549-3653-4044-b913-faf09cee25a3" width="50%" height="50%">
</p>

- 每个需要在平台上发布的应用，都需要在本仓库下的 `XRApps` 中创建一个文件夹，并在文件夹中包含相关文件。为了防止文件夹名称重复，我们建议你将文件夹命名为具有唯一性质的名字，如 Bundle ID。下面是文件夹的基本结构：

```other
Folder
  - meta.json 
  - info.json
  - icon.png
  - some_photo.png
```

- `meta.json` 用来储存应用的基本元信息，主要被用来标识应用和检索使用。下面是一个示例文件：

```other
{
    "id": "579271a6-b86a-4dae-bbed-f856e830b42d",
    "name": "HelloWorld",
    "icon": "icon.png",
    "version": "1.0.0",
    "compileVersion": "21N5259i",
    "repo": "https://github.com/XRealityZone/what-vision-os-can-do",
    "category": "Developer",
    "bundle": "zone.xreality.WhatVisionOSCanDo",
    "featuredImage": "helloworld-feature.png",
    "slogan": "Meet the visionOS",
}
```

以下是对于各字段用法的解释：

| **字段名称**      | **是否必要** | **用途**                                                                                                                                                                          |
| ------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id            | 必要       | 应用标识，为 UUID 字符串，需自行生成，不能重复；推荐使用 [Online UUID Generator](https://www.uuidgenerator.net/) 的 V4 版本生成 UUID                                                                          |
| name          | 必要       | 应用名称                                                                                                                                                                            |
| icon          | 必要       | 应用图标，推荐大小为512 * 512，自动裁切为圆形，目前还不支持填写图片链接，需要将所有图片存到文件夹中，并在 JSON 文件中使用相对路径调用。                                                                                                     |
| version       | 必要       | 应用当前版本，支持  `A.B` 和 `A.B.C` 两种格式                                                                                                                                                 |
| compileVersion| 必要       | 当前 App 对应的 visionOS 模拟器版本号，通过 `Xcode` -> `Setting` -> `Platforms` 里的界面查看具体信息 |
| repo          | 必要       | 应用的 GitHub Repo 地址，用于下载应用，该 Repo 无需包含源代码，但必须完成 [在 GitHub 上发布你的产品](craftdocs://open?blockId=F105C081-C8B4-4D9F-9959-DDB95508E30F&spaceId=23c2d78f-f0b2-a42c-f2cb-f0b2393adf52)  |
| category      | 必要       | 应用分类，必须从以下字段中选择：`Play`，`Work`，`Create`， `Develop`                                          |
| bundle        | 必要       | 上传应用的 Bundle ID                                                                                                                                                                 |
| featuredImage | 非必要      | 应用精选图片，推荐大小为 1300*800，如不添加，应用将不会在首页精选区展示，每张图片请控制在 1MB 以内；目前还不支持填写图片链接，需要将所有图片存到文件夹中，并在 JSON 文件中使用相对路径调用。                                                                        |
| slogan        | 非必要      | 应用标语，如果填写了 `featuredImage` 则必须填写该字段                                                                                                                                             |

- `info.json` 用来储存应用基本内容信息，将会被渲染并展示于应用详情页面。下面是一个示例文件：

```other
{
    "author": "Ryan Zhu",
    "description": "Unlock the full potential of your vision with EyeSight, a groundbreaking vision OS app designed to enhance and manage your visual experiences in real-time. EyeSight leverages the most advanced artificial intelligence and machine learning algorithms to analyze and interpret visual data, providing you with a host of functionalities that will redefine the way you see the world.\nKey Features:\nEnhanced Visual Perception: EyeSight uses real-time image processing and computer vision algorithms to optimize the images and videos you see, adjusting contrast, brightness, and sharpness to provide a clearer, more detailed view of your surroundings.\nObject and Text Recognition: EyeSight can identify and categorize objects and text in your field of vision, providing you with relevant information and context about what you are looking at.",
    "developerWebsite": "https://apple.com",
    "images": ["1.png", "2.png", "3.png"]
}
```

以下是对于各字段用法的解释：

| **字段名称**         | **是否必要** | **解释**                                                               |
| ---------------- | -------- | -------------------------------------------------------------------- |
| author           | 必要       | 应用开发者名称                                                              |
| description      | 必要       | 应用简介，可使用转义字符                                                         |
| developerWebsite | 必要       | 开发者网站                                                                |
| images           | 必要       | 应用截图，每张图片请控制在 1MB 以内；目前还不支持填写图片链接，需要将所有图片存到文件夹中，并在 JSON 文件中使用相对路径调用。 |

- 提交 commit 到自己的分支和仓库中，并在自己的仓库中发起向 XRealityZone 仓库的 PR 请求。

<p align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/a3c9bfdd-3a44-455b-9c91-72dff117e9fa" width="50%" height="50%">
</p>

<p align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/3d45a8ab-2120-4a25-bcdf-6417b505c614" width="50%" height="50%">
</p>

- 等待 XReality.Zone 的工作人员 Review 和 Merge 你的 PR，一旦你的 PR 被合入，就代表你的应用上架到了我们的交流平台。

<p align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/cafcd476-ae58-466c-a552-26544e20fc7a" width="50%" height="50%">
</p>

## FAQ

**Q：在哪里能找到当前应用在 visionOS 模拟器下的二进制文件？**

A：获取模拟器版本的二进制文件分为 3 步：

- 点击左上角的 `Run` 按钮或者使用快捷键 `CMD + R` 运行你的 visionOS 程序，确保代码运行的平台为 visionOS 模拟器平台。

<p align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/7fac429c-04d0-4a5d-bd26-b1cae603bb79" width="50%" height="50%">
</p>

- 在出现 `Build Succeeded` 的提示框后，展开左侧导航栏里的 `Product` 文件夹，在这个目录下会有一个或多个应用（以 `.app` 为后缀的文件）存在，选择你的 visionOS 应用，右键点击并选择 `Show in Finder`按钮。

<p align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/c216a253-1fe3-4873-8dc1-098e63b4173a" width="50%" height="50%">
</p>

- 在此文件夹里的 `.app` 文件，即为当前应用在 visionOS 模拟器下的二进制文件。

**Q: 如何找到仓库里的 Release 界面？**

A: 在仓库首页可以找到 `Release` 区域，点击后即可进入到 `Release` 界面。

<p align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/f6dec8ee-cebd-49e3-8e73-482392930444" width="50%" height="50%">
</p>

**Q：如何在自己的仓库里创建 tag**

A：在 `Release` 界面点击 `Choose a tag`，并在下拉列表的文本框里填写版本号，在填写完毕后，点击 `+ Create new tag A.B.C on publish` ，目前支持 `A.B` 和 `A.B.C` 两种格式的版本号，请保持版本号的顺序增长，不要出现倒序的情况。

<p align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/5b86c3fb-d4f9-4b03-8147-1aa2b6a2aa0b" width="50%" height="50%">
</p>

**Q: 如何查找 compileVersion 或 visionOS 模拟器的版本？**

A: 打开 Xcode 并通过 `Xcode` -> `Setting` -> `Locations` 找到 visionOS 模拟器。

<div align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/c05c1be1-b7e7-4398-b616-f916983dcc34" width="50%" height="50%">
</div>
