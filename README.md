# App Submission Guide

> * If you are proficient in English, please read the [English version](https://github.com/XRealityZone/XRApps/blob/main/README.md) of the instructions.
> * If you are proficient in Chinese, please read the [Chinese version](https://github.com/XRealityZone/XRApps/blob/main/README_CN.md) of the instructions.
> * If you are proficient in Japanese, please read the [Japanese version](https://github.com/XRealityZone/XRApps/blob/main/README_JP.md) of the instructions.

## Welcome to Join Us

The release of Apple Vision Pro heralds the advent of the spatial computing era, prompting tech enthusiasts and developers to contemplate how to create unique three-dimensional applications on new interactions, systems, and hardware.

Since the WWDC 2023 keynote, social media has been flooded with beautiful mockups and demo videos of visionOS Apps. However, it's challenging to try other developers' creations because the Apple Vision Pro hasn't been officially released yet.

To address this issue, we developed the Let's xrOS App. Through it, you can try out visionOS Apps created by other community members and get an early taste of the allure of spatial computing devices.

We hope this tool will foster more frequent communication among developers and promote the growth of the entire community.

Let's xrOS is a platform for exchanging visionOS applications, allowing you to distribute your developed visionOS apps to enthusiasts worldwide.

> Tip 1: **Note that you do not need to upload the application body to this repository; moreover, Let’s xrOS does not force you to open source your application. You only need to upload the basic metadata to start distributing your application.**
> 
> Tip 2: This is the application retrieval repository for Let’s xrOS. If you wish to **publish or update** your application on Let’s xrOS, you need to submit the related metadata files to this repository.
> 
> Tip 3: If you want to download Let's xrOS applications, you can do so from the release page of [this repository](https://github.com/XRealityZone/Let-us-xrOS). With this application, you can explore other developers' visionOS applications.

## Publishing Your Product on GitHub

- Run your project to locate the binary file of your current application under the visionOS simulator, compress it into a ZIP file named `app.zip`, and ensure the package name is unchanged to avoid indexing errors.(If you don't know how to do, please look at [first question of Q&A](https://github.com/XRealityZone/XRApps/tree/main#faq) )

<div align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/1faeadfa-2fca-4016-80b5-710622c3a55d" width="50%" height="50%">
</div>


- Create a repository for the current app on GitHub (if you've already done so, skip this step). Ensure the repository is of `Public` type, as private ones will fail the app information retrieval.

<div align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/1e6d4e10-9bbf-4951-a832-e54b9cad488a" width="50%" height="50%">
</div>

- Navigate to the `Release` page of the repository, select the tag to be released, and upload the `app.zip` package prepared earlier, filling in the corresponding Release version name (recommended to keep it the same as the tag number).

<div align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/274944f9-dc0f-4c39-b008-1d9e4135663c" width="50%" height="50%">
</div>


## Submitting Your App Information to XReality.Zone's Source

- Fork the [XRApps repository](https://github.com/XRealityZone/XRApps) at XReality.Zone.

<div align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/12e7e8a5-05b3-404b-9416-711638511e0d" width="50%" height="50%">
</div>

- Clone the forked repository locally and create a new branch, naming it `app/Your_App’s_Bundle_ID`.

<div align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/404f8549-3653-4044-b913-faf09cee25a3" width="50%" height="50%">
</div>

- Each app to be published on the platform needs to have a folder in `XRApps` containing relevant files. To avoid folder name duplication, it is recommended to name the folder with a unique identifier, such as the Bundle ID. Here's the basic folder structure:

```plaintext
Folder
  - meta.json 
  - info.json
  - icon.png
  - some_photo.png
```

- `meta.json` stores the basic metadata of the app, mainly used for identification and retrieval. Here's an example file:

```plaintext
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

The explanation for each field's usage is as follows:

| Field Name     | Required | Usage                                                                                                                    |
| -------------- | -------- | ------------------------------------------------------------------------------------------------------------------------ |
| id             | Yes      | Application identifier, a UUID string, which must be generated by the user and unique; use [Online UUID Generator](https://www.uuidgenerator.net/) for UUID generation. |
| name           | Yes      | Application name                                                                                                         |
| icon           | Yes      | Application icon, recommended size is 512x512, will be cropped to a circle; currently, image links are not supported, store all images in the folder and call them using relative paths in the JSON file. |
| version        | Yes      | Current application version, supports `A.B` and `A.B.C` formats.                                                         |
| compileVersion | Yes      | The current App corresponds to the version number of the visionOS simulator, you can check the specific information through the interface in `Xcode` -> `Setting` -> `Platforms`.                                                         |
| repo           | Yes      | GitHub Repo URL for downloading the app; this repo does not need to contain the source code.                             |
| category       | Yes      | Application category, must choose from `Play`, `Work`, `Create`, `Develop`.                                              |
| bundle         | Yes      | The Bundle ID of the uploaded app.                                                                                       |
| featuredImage  | No       | Featured image of the app, recommended size is 1300x800; images should be under 1MB; currently, image links are not supported. |
| slogan         | No       | App slogan, required if `featuredImage` is provided.                                                                     |

- `info.json` stores the basic content information of the app, which will be rendered and displayed on the app detail page. Here's an example file:

```other
{
    "author": "Ryan Zhu",
    "description": "Unlock the full potential of your vision with EyeSight, a groundbreaking vision OS app designed to enhance and manage your visual experiences in real-time. EyeSight leverages the most advanced artificial intelligence and machine learning algorithms to analyze and interpret visual data, providing you with a host of functionalities that will redefine the way you see the world.\nKey Features:\nEnhanced Visual Perception: EyeSight uses real-time image processing and computer vision algorithms to optimize the images and videos you see, adjusting contrast, brightness, and sharpness to provide a clearer, more detailed view of your surroundings.\nObject and Text Recognition: EyeSight can identify and categorize objects and text in your field of vision, providing you with relevant information and context about what you are looking at.",
    "developerWebsite": "https://apple.com",
    "images": ["1.png", "2.png", "3.png"]
}
```

Here is the translated content in English, retaining the markdown (md) format:

Explanation of each field's use:

| **Field Name**       | **Required** | **Explanation**                                                               |
| -------------------- | ------------ | ------------------------------------------------------------------------------ |
| author               | Yes          | Name of the app developer                                                      |
| description          | Yes          | Introduction of the app, escape characters can be used                         |
| developerWebsite     | Yes          | Developer's website                                                           |
| images               | Yes          | App screenshots, each image should be controlled within 1MB; currently, image links are not supported, all images need to be stored in a folder, and called in the JSON file using relative paths. |

- Commit your changes to your branch and repository, and initiate a pull request (PR) to the XRealityZone repository from your repository.

<div align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/a3c9bfdd-3a44-455b-9c91-72dff117e9fa" width="50%" height="50%">
</div>

<div align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/3d45a8ab-2120-4a25-bcdf-6417b505c614" width="50%" height="50%">
</div>

- Wait for the staff at XReality.Zone to review and merge your PR. Once your PR is merged, it signifies that your app has been listed on our exchange platform.

<div align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/cafcd476-ae58-466c-a552-26544e20fc7a" width="50%" height="50%">
</div>

## FAQ

**Q: Where can I find the binary file of the current app under the visionOS simulator?**

A: Method 1: Find the binary file in Product -> Show Build Folder in Finder

<p align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/f79fe5c4-3ced-4003-a465-71fd10b34b79" width="50%" height="50%">
</p>

Method 2: Getting the binary file for the simulator version involves 3 steps:


- Click the `Run` button in the upper left corner or use the shortcut `CMD + R` to run your visionOS program, making sure the platform for code execution is the visionOS simulator platform.

<div align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/7fac429c-04d0-4a5d-bd26-b1cae603bb79" width="50%" height="50%">
</div>

- After the `Build Succeeded` prompt appears, expand the `Product` folder in the left navigation bar. In this directory, there will be one or more applications (files with a `.app` suffix), select your visionOS application, right-click and choose the `Show in Finder` button.

<div align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/c216a253-1fe3-4873-8dc1-098e63b4173a" width="50%" height="50%">
</div>

- The `.app` file in this folder is the binary file of the current app under the visionOS simulator.

**Q: How to find the Release page in the repository?**

A: The `Release` area can be found on the homepage of the repository. Clicking it will take you to the `Release` page.

<div align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/f6dec8ee-cebd-49e3-8e73-482392930444" width="50%" height="50%">
</div>

**Q: How to create a tag in my repository?**

A: Click on `Choose a tag` in the `Release` page, and fill in the version number in the dropdown list's textbox. After filling it out, click `+ Create new tag A.B.C on publish`. Currently, version numbers in the format `A.B` and `A.B.C` are supported. Please ensure the version number increases in order and does not regress.

<div align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/5b86c3fb-d4f9-4b03-8147-1aa2b6a2aa0b" width="50%" height="50%">
</div>

**Q: How to find compileVersion or visionOS Simulator's Version?** 

A: Open Xcode and find visionOS Simulator through `Xcode` -> `Setting` -> `Locations`.

<div align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/c05c1be1-b7e7-4398-b616-f916983dcc34" width="50%" height="50%">
</div>
