# KiCad チートシート

KiCadのチートシート

## 環境

- KiCad 5.1.5
- macOS Catalina 10.15.3

## 使えるリンク

- KiCadチュートリアル：[URL](https://sites.google.com/site/vita0117KiCad/home)
- KiCad：[URL](http://penguin.tantin.jp/hard/KiCad.html)
- KiCad Wiki：[URL](http://wiki.kicad.jp/%E3%83%A1%E3%82%A4%E3%83%B3%E3%83%9A%E3%83%BC%E3%82%B8)

## 回路図(eeschema)

### 回路図コマンド

- g：Drag：部品の移動（ワイヤーの接続状態を保ったまま）
- m：Move：部品の移動（ワイヤーの接続状態は切れる）
- u：Reference：部品名の変更
- v：Value：値の変更
- f：Footprint：フットプリントの変更
- b：Bus：バス配線
- w：Begin Wire：ワイヤー配線開始
- k：End Wire：ワイヤー配線終了
- c：Copy：コピー
- [DEL]：DELETE：削除
- ↑+A：部品の追加w
- x：x軸基準反転
- y：y軸基準反転

### 回路図Tips

- シート設定
  - シートサイズ：左上 Page SettingsからSheet Sizeを変更する
    - A4は小さいので, A3にとりあえず変更するのが無難そう
  - 署名：名前や日付を更新できる

## 基板図(pcbnew)

### 基板図コマンド

- ↑+X：配線
- n：グリッドの変更
- {：配線の透明度を上げる
- }：配線の透明度を下げる
- v：レイヤーの選択変更(TopとBottomをトグル)

### 基板図Tips

- Show filled areas in zones(左メニュー)：ベタの表示・非表示
- View→Flip Board View：基板の反転

## 部品

## Gerber

- KiCadからガーバーファイルを出力する方法：[URL](http://support.seeedstudio.com/knowledgebase/articles/1187731-KiCad%E3%81%8B%E3%82%89%E3%82%AC%E3%83%BC%E3%83%90%E3%83%BC%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%82%92%E5%87%BA%E5%8A%9B%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95)
- 手順
  1. Gerberファイルの出力：pcbnew：File→Plot→Plot
      - User Protel filename extensiosにチェック
  2. Drillファイルの出力：pcbnew：File→Plot→Generate Drill Files→Generate Drill File
      - PTH and NPTH in sigle fileにチェックチェック

## 3D

- KiCadからFusion 360：[URL](https://garchiving.com/output-3d-model-with-KiCad/)
- STEPファイル作成：[URL](https://denshikousakusenka.jimdofree.com/%E9%96%8B%E7%99%BA%E7%92%B0%E5%A2%83%E6%A7%8B%E7%AF%89/KiCad/3d-cad%E3%81%B8%E3%83%87%E3%83%BC%E3%82%BF%E7%A7%BB%E8%A1%8C/)
- 手順
  1. STEPファイルの出力：pcbnew：File→Export→STEP
  1. 3Dモデルの閲覧：pcbnew：View→3D Viewer
  1. JPEG・PNGの出力：3D Viewer：File→Export Current View as ...
      1. 部品を非表示にする
      1. ど真ん中に表示する

## その他

- KiCad テキスト はじめて編：[URL](https://qiita.com/akbrobot/items/89d5f08f5c64227a56ee)
- DCジャック変換基板：[URL](http://www.kicad-de-kiban.net/archivescat_DC%E3%82%B8%E3%83%A3%E3%83%83%E3%82%AF%E5%A4%89%E6%8F%9B%E5%9F%BA%E6%9D%BF.html)
- KiCADのベタグランドおよびビアの追加方法：[URL](http://www.kicad.xyz/entry/betagnd-and-via/)
- KiCadのパターン配線方法：[URL](http://www.KiCad.xyz/entry/patern-haisen/)
- べタ・パターンを作る！：[URL](https://sites.google.com/site/vita0117KiCad/home/9)
- teardrops：[URL](https://github.com/NilujePerchut/kicad_scripts/tree/master/teardrops)
- 複数基板：[URL](https://lowreal.net/2016/07/25/1)
- 階層シート：[URL](http://wiki.kicad.jp/Eeschema_Chapter6_JA)
- 外径の作成：[URL](https://kicad.txplore.com/index-p=113.html)
