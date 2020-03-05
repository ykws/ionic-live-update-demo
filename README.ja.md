# Ionic Live Update Demo

[![macOS](https://img.shields.io/badge/macOS-Catalina-black)](https://developer.apple.com/macos/)

> Ionic Appflow's Deploy feature makes it easy to deploy app updates in real time without going through a traditional app store submission process for the vast majority of business logic, UI, and style changes.
>
> Note: The Deploy feature only works on binary compatible changes (HTML, CSS, JS), meaning if you rely on native code updates you must resubmit to the app store first before using Deploy.
>
> [Deploy a Live Update](https://ionicframework.com/docs/appflow/quickstart/deploy)

## Get Started 
1. [Create a free Ionic account](https://ionicframework.com/getting-started#account)
2. [Connect Your Repo](https://ionicframework.com/docs/appflow/quickstart/connect)
3. [Install the Appflow SDK](https://ionicframework.com/docs/appflow/quickstart/installation)
4. [Push a Commit](https://ionicframework.com/docs/appflow/quickstart/push)
5. [Deploy a Live Update](https://ionicframework.com/docs/appflow/quickstart/deploy)

## Supported
**All cases**
* Simulator
* Debug running
* TestFlight
* App Store

## Examples
Ionic で Live Update を試す一例です。
細かい部分は適宜読み替えてください。

### Ionic プロジェクト作成
Live Update の確認なので好きなテンプレートからプロジェクトを作成します。
`ionic serve` でブラウザで初期状態の表示を確認しておきます。

```
$ ionic start ionic-live-update-demo tabs --type=react --capacitor
$ ionic serve
```

### iOS向け設定
iOSアプリの Live Update を試したいので iOS 向けに設定します。

```
$ ionic build --prod
$ npx cap add ios
$ npx cap open ios
```

実機で試す場合は以下を設定しておきます。
Simulator で確認する場合は不要です。

* `Bundle Identifier`
* `Signing Team`

### Ionic Hub と接続
Live Update は Ionic Hub で Build した内容が Deployment されることで Appflow をバンドルした iOS アプリが自動更新する仕組みになっているため、 Ionic Hub とつなぎます。
`ionic link` 以下は Ionic Hub でのアプリIDなので自身の環境のIDを指定します。

```
$ ionic link 68de2b8d
$ git push ionic master
```

### Appflow SDKをインストール
Live Update を有効にするためにアプリに Appflow を組み込みます。

```
$ ionic deploy add --app-id="68de2b8d" --channel-name="Production" --update-method="auto"
$ git push ionic master
```

ここまでできれば、あとは以下の手順で Live Update が試せます。

* ローカルで変更してコミット
* ローカルから Ionic Hub に push
* Ionic Hub で Build と Deployment

iOSアプリは更新しなくても、 Ionic から変更が反映されるようになります。
