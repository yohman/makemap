# Webマップを作ってみよう！

<kbd><img src="images/banner.png"></kbd>

[Intro to Mapping Workshop](https://docs.google.com/presentation/d/16YADgSqYe1pGUYNRoaKFPs8R3k0JVYjPrpHeMqE0RAE/edit?usp=sharing)

## Step 1

デスクトップまたはコンピュータ上の任意の場所に「map」フォルダを作成します。 ここに、このワークショップ用のファイルを保存します。

## Step 2

VSCodeを開きます。VSCode をお持ちでない場合は、ここからダウンロードできます:

   - [VSCode](https://code.visualstudio.com/download)

## Step 3

1. 「フォルダーを開く」をクリックします
1. ステップ 1 で作成した「map」フォルダーに移動します。
1. 以下に示すように、「新規ファイル」ボタンをクリックします。


<kbd><img src="images/vscode start.png" width=600></kbd>

4. ファイル名を「map.html」にします。

VSCode は次のようになります。

<kbd><img src="images/map file.png" width=600></kbd>

## Step 4

次のコードをコピーして貼り付けます。


```html
<!-- leaflet css -->
<link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />

<!-- leaflet javascript -->
<script src="https://unpkg.com/leaflet@1.4.0/dist/leaflet.js"></script>

<!-- マップはここで表示 -->
<div id="map" style="width: 100%; height: 600px;"></div>

<!-- マップを作るjavascript -->
<script>
	// 地図の中心になる緯度経度
	var latlon = [35.6585, 139.7454]

	// マップを作成
	var map = L.map('map').setView(latlon, 18);

	// ベースマップ（衛生写真）を追加
	L.tileLayer('https://cyberjapandata.gsi.go.jp/xyz/seamlessphoto/{z}/{x}/{y}.jpg', {
		attribution: '国土地理院'
	}).addTo(map);

	// マーカーを追加
	L.marker(latlon).addTo(map)
		.bindPopup("Tokyo Tower")
		.openPopup();
</script>

```

## Step 5

ファイルを保存します。 デスクトップ (または使用することを選択した場所) で「map.html」ファイルを見つけてダブルクリックします。ブラウザーでマップが現れるはず！

## Step 6

マップをカスタマイズしよう。まずは地球上の好みの場所の緯度と経度を調べます。

Googleマップにアクセス: [https://www.google.com/maps](https://www.google.com/maps)

場所を検索またはそこに移動。

地図で見つけた場所を右クリックして座標を選択（自動的にクリップボードにコピーされます）。

<kbd><img src="images/reitaku coords.png" width=600></kbd>

## Step 7

コード内の緯度と経度の座標を、Google マップからコピーした数値に置き換えて、ファイルをセーブして、もう一度ブラウザーに戻り、リフレッシュ！

<img src="images/code coords.png" width=400>

## Step 8

いくつかのチャレンジ演習:

- タイトルと説明を追加しよう (HTML タグ `<h1></h1>`、`<p></p>` を使用する)。
- ポップアップウィンドウ（bindPopup）のテキストを変更する
- 複数のマーカーを地図に追加する
- 地図に円を追加する (以下の例、半径はピクセル単位です)

```
// add a circle 
L.circleMarker(latlon,{radius:100}).addTo(map)
```

## Step 9

地図のスクリーンショットを撮り、この Google スライドに投稿しよう！

https://docs.google.com/presentation/d/1rTvHOYbw_6Ghe2DUFVIWSTxmtYxGbS0_tU8WJZCJ2y4/edit?usp=sharing

## Discussion

- 今作成したものがどのように役立つかどうかの理由を説明してください
- 「インタラクティブ」マップは普通の地図とどのような【違い】があるのでしょうか?
- マップに追加したい機能について話し合う
- このタイプのデータ視覚化 (つまり、マップベース) を興味のある分野でどのように使用できるかを詳しく語り合おう。