# アプリ提出ガイド

> * 英語に精通している場合は、[英語版](https://github.com/XRealityZone/XRApps/blob/main/README.md)の説明をお読みください。
> * 中国語に精通している場合は、[中国語版](https://github.com/XRealityZone/XRApps/blob/main/README_CN.md)の説明をお読みください。
> * 日本語に精通している場合は、[日本語版](https://github.com/XRealityZone/XRApps/blob/main/README_JP.md)の説明をお読みください。

## あなたの参加を歓迎します

Apple Vision Pro のリリースは、空間コンピューティング時代の到来を予告し、テクノロジーエンスージアストと開発者が新しいインタラクション、システム、ハードウェアで独自の3Dアプリをどう作るか考え始めました。

WWDC 2023の発表以降、ソーシャルメディアには多くの美しいvisionOSアプリのモックアップとデモビデオが溢れていますが、Apple Vision Proはまだ正式にリリースされていないため、他の開発者の作品を試すことは困難です。

この問題を解決するため、私たちはLet’s xrOSというアプリを開発しました。これにより、コミュニティ内の他のクリエイターが開発したvisionOSアプリを試し、空間コンピューティングデバイスの魅力を一足先に体験することができます。

このツールを通じて、開発者間のコミュニケーションがより頻繁になり、コミュニティ全体の発展を促進したいと考えています。

Let’s xrOSはvisionOSアプリの交流プラットフォームで、あなたが開発したvisionOSアプリを世界中のエンスージアストに配布することができます。

このリポジトリは、Let’s xrOSのアプリ検索リポジトリです。Let’s xrOSで**公開、配布、または更新**する場合、関連するメタ情報ファイルをこのリポジトリに提出する必要があります。

> 注意：アプリ本体をこのリポジトリにアップロードする必要はありません。また、Let’s xrOSはアプリをオープンソースにすることを強制しません。基本的なメタ情報をアップロードするだけでアプリの配布を開始できます。

## GitHubで製品を公開する

- プロジェクトを実行し、visionOSシミュレータでの現在のアプリケーションのバイナリファイルを見つけ、それを`app.zip`という名前のZIPパッケージに圧縮し、パッケージ名を変更しないようにしてください。それ以外の場合、アプリ情報の検索に失敗します（操作方法がわからない場合は、[FAQの最初の質問](https://github.com/XRealityZone/XRApps/blob/main/README_CN.md#faq)を参照してください）。

<p align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/1faeadfa-2fca-4016-80b5-710622c3a55d" width="50%" height="50%">
</p>

- GitHubで現在のアプリのリポジトリを作成します（既に作成している場合はこのステップをスキップしてください）。リポジトリのタイプが`Public`であることを確認してください。それ以外の場合、アプリ情報の検索に失敗します。

<p align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/1e6d4e10-9bbf-4951-a832-e54b9cad488a" width="50%" height="50%">
</p>

- リポジトリの`Release`ページに移動し、リリースするタグ番号を選択し、事前に準備した`app.zip`圧縮パッケージをアップロードし、対応するReleaseバージョン名を記入します（この名前はタグ番号と同じにすることを推奨します）。

<p align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/274944f9-dc0f-4c39-b008-1d9e4135663c" width="50%" height="50%">
</p>

## アプリ情報をXReality.Zoneの情報源に提出する

- XReality.Zoneの[XRAppsリポジトリ](https://github.com/XRealityZone/XRApps)をフォークします。

<p align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/12e7e8a5-05b3-404b-9416-711638511e0d" width="50%" height="50%">
</p>

- フォーク後のリポジトリをローカルにクローンし、新しいブランチを作成します。ブランチ名は`app/Your_App’s_Bundle_ID`の形式にします。

<p align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/404f8549-3653-4044-b913-faf09cee25a3" width="50%" height="50%">
</p>

- プラットフォーム上で公開する必要がある各アプリは、`XRApps`の下にフォルダを作成し、関連するファイルを含める必要があります。フォルダ名が重複しないように、Bundle IDのような一意性を持つ名前でフォルダを命名することをお勧めします。以下はフォルダの基本構造です：

```other
Folder
  - meta.json 
  - info.json
  - icon.png
  - some_photo.png
```

`meta.json`はアプリの基本的なメタ情報を保存するために使用され、主にアプリの識別と検索に使用されます。以下は例のファイルです：

```other
{
    "id": "579271a6-b86a-4dae-bbed-f856e830b42d",
    "name": "HelloWorld",
    "icon": "icon.png",
    "version": "1.0.0",
    "repo": "https://github.com/XRealityZone/what-vision-os-can-do",
    "category": "Developer",
    "bundle": "zone.xreality.WhatVisionOSCanDo",
    "featuredImage": "helloworld-feature.png",
    "slogan": "Meet the visionOS",
}
```

以下は各フィールドの使用法についての説明です：

| **フィールド名**      | **必要か** | **用途**                                                                                                                                                                          |
| ---------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id               | 必要       | アプリの識別子で、UUIDの文字列で、ユーザー自身が生成し、重複してはいけません；[Online UUID Generator](https://www.uuidgenerator.net/) の V4 を使用して UUID を生成することを推奨します。 |
| name             | 必要       | アプリ名                                                                                                                                                                          |
| icon             | 必要       | アプリのアイコンで、512 * 512 のサイズを推奨し、円形に自動カットされます。現在は画像リンクの記入には対応しておらず、すべての画像をフォルダに保存し、JSONファイルで相対パスを使用して呼び出す必要があります。                                          |
| version          | 必要       | アプリの現在のバージョンで、`A.B` と `A.B.C` の2つのフォーマットをサポートしています。                                                                                                    |
| repo             | 必要       | アプリの GitHub Repo のアドレスで、アプリをダウンロードするために使用されます。この Repo はソースコードを含む必要はありませんが、[GitHubで製品を公開する](craftdocs://open?blockId=F105C081-C8B4-4D9F-9959-DDB95508E30F&spaceId=23c2d78f-f0b2-a42c-f2cb-f0b2393adf52) が完了している必要があります。 |
| category         | 必要       | アプリのカテゴリーで、以下のフィールドから選択する必要があります：`Play`、`Work`、`Create`、`Develop`                                                                                        |
| bundle           | 必要       | アプリの Bundle ID                                                                                                                                                               |
| featuredImage    | 不要       | アプリの特集画像で、1300*800 のサイズを推奨し、追加しない場合、アプリはホームページの特集エリアに表示されません。各画像は1MB以内に抑えてください；現在は画像リンクの記入には対応しておらず、すべての画像をフォルダに保存し、JSONファイルで相対パスを使用して呼び出す必要があります。                                 |
| slogan           | 不要       | アプリのスローガンで、`featuredImage`を記入した場合は、このフィールドを記入する必要があります。                                                                                                            |

`info.json`はアプリの基本内容情報を保存するために使用され、アプリの詳細ページでレンダリングされ表示されます。以下は例のファイルです：

```other
{
    "author": "Ryan Zhu",
    "description": "EyeSightで、あなたの視覚の完全な可能性を解き放ちましょう。EyeSightは、リアルタイムで視覚体験を強化・管理するために設計された画期的なvision OSアプリです。最先端の人工知能と機械学習アルゴリズムを活用して視覚データを分析・解釈し、世界を見る方法を再定義する機能を提供します。\n主な特徴：\n視覚認識の強化：EyeSightはリアルタイムの画像処理とコンピュータビジョンアルゴリズムを使用して、見ている画像やビデオを最適化し、コントラスト、明るさ、鮮明さを調整して、周囲をよりクリアで詳細な視界を提供します。\nオブジェクトとテキストの認識：EyeSightは視界内のオブジェクトとテキストを識別・分類し、見ているものに関する関連情報と文脈を提供します。",
    "developerWebsite": "https://apple.com",
    "images": ["1.png", "2.png", "3.png"]
}
```

以下は、各フィールドの使用法についての説明です：

```markdown
| **フィールド名**       | **必要か** | **説明**                                                                   |
| ------------------- | -------- | ------------------------------------------------------------------------ |
| author              | 必要       | アプリ開発者の名前                                                            |
| description         | 必要       | アプリの紹介で、エスケープ文字を使用可能                                             |
| developerWebsite    | 必要       | 開発者のウェブサイト                                                          |
| images              | 必要       | アプリのスクリーンショットで、各画像は1MB以内にしてください；現在は画像リンクの記入はサポートしておらず、全ての画像をフォルダに保存し、JSONファイルで相対パスを使用して呼び出す必要があります。 |
```

- 自分のブランチとリポジトリにコミットを提出し、自分のリポジトリからXRealityZoneのリポジトリへのPRリクエストを開始します。

<p align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/a3c9bfdd-3a44-455b-9c91-72dff117e9fa" width="50%" height="50%">
</p>

<p align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/3d45a8ab-2120-4a25-bcdf-6417b505c614" width="50%" height="50%">
</p>

- XReality.ZoneのスタッフがあなたのPRをレビューし、マージするのを待ちます。あなたのPRがマージされたら、あなたのアプリが私たちの交流プラットフォームに掲載されたことを意味します。

<p align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/cafcd476-ae58-466c-a552-26544e20fc7a" width="50%" height="50%">
</p>

## FAQ

**Q：visionOSシミュレーターで現在のアプリのバイナリファイルをどこで見つけることができますか？**

A：シミュレーターバージョンのバイナリファイルを取得するには3つのステップがあります：

- 左上隅の `Run` ボタンをクリックするか、または `CMD + R` のショートカットキーを使用してあなたのvisionOSプログラムを実行し、コードの実行プラットフォームがvisionOSシミュレーターであることを確認してください。

<p align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/7fac429c-04d0-4a5d-bd26-b1cae603bb79" width="50%" height="50%">
</p>

- `Build Succeeded` のプロンプトが表示された後、左側のナビゲーションバーの `Product` フォルダを展開します。このディレクトリには、1つまたは複数のアプリケーション（`.app` というサフィックスのファイル）が存在します。あなたのvisionOSアプリを選択し、右クリックして `Show in Finder` ボタンを選択します。

<p align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/c216a253-1fe3-4873-8dc1-098e63b4173a" width="50%" height="50%">
</p>

- このフォルダ内の `.app` ファイルが、visionOSシミュレーター下での現在のアプリのバイナリファイルです。

**Q: リポジトリの `Release` インターフェースはどこで見つけることができますか？**

A: リポジトリのホームページで `Release` エリアを見つけることができます。クリックすると `Release` インターフェースに入ることができます。

<p align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/f6dec8ee-cebd-49e3-8e73-482392930444" width="50%" height="50%">
</p>

**Q：自分のリポジトリでどのようにしてタグを作成しますか？**

A：`Release` インターフェースで `Choose a tag` をクリックし、ドロップダウンリストのテキストボックスにバージョン番号を入力します。入力が完了したら、`+ Create new tag A.B.C on publish` をクリックします。現在、`A.B` および `A.B.C` の2つの形式のバージョン番号をサポートしています。バージョン番号は順番に増やし、逆順にならないようにしてください。

<p align="center">
  <img src="https://github.com/XRealityZone/XRApps/assets/11788119/5b86c3fb-d4f9-4b03-8147-1aa2b6a2aa0b" width="50%" height="50%">
</p>                                                             
