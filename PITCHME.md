@snap[north-west]
@size[0.8em](クラメソ夏のブログ祭り 〜ブログの書き方全てさらけ出せ！〜)
@snapend

@snap[west]
# 泡沫エンジニアブログ書きが普段どうやってるか晒す

2019.08.09
@snapend

@snap[south]
<font size="-1">© 2019 Classmethod, Inc.</font>
@snapend

---?image=assets/img/profile_3a2p3s.png&position=right&size=35%
### About

@snap[west]
@ul[list](false)
- **渡辺聖剛 (Watanabe, Seigo)**
  - AWS事業本部 オペレーション部
  - 入社 2017.1 (2y8m)
  - 記事公開 140本程度
  - RANK 79
  - 緑13/赤6/銀1 (/殿堂入り1)
@ulend
@snapend

---
### Spec.

@ul[list](false)
- 使える(た) Adobe 製品
  - Ps / AI / Pr / AE / DW / FW
- 好きな Adobe 製品
  - AfterEffects CS
- 入社前の関係しそうな略歴
  - ~~同人小説書き (黒歴史)~~
  - 某 MMORPG 関連ブログ (3y+)
  - ~~某ゲーム系 MAD のニコ動作家（2y+）~~
- CM 採用一次面接で答えた「最近読んで面白かった本」
  - インタフェースデザインの心理学 (O'Reilly)
@ulend

---
### Goal

@snap[west]
ブログが書けなくて四半期ごとに夜な夜なおびえている CM 社員が  
「**ああこんな書き方してても大丈夫なやつがいるんだ**」  
と解放された気分で朝を迎えることができるようになること
@snapend

---
### Agenda

@ul[list](false)
- 道具
  - ハードウェア
  - ソフトウェア
- 書き方
@ulend

---

@snap[west]
## 道具(ハードウェア)
@snapend

---?image=assets/img/IMG_1909.JPG&position=bottom&size=60%
### 道具(ハードウェア)

Note:
- カメラ = スマフォ (iPhone)
  - プレゼンのスクリーン以外にもいろいろ撮影
    - 文字だらけの記事にしないため（読むときのリズム重点）
  - Pros
    - AirDrop (や連携カメラ)でデータ転送に Wi-Fi / リーダ不要
    - 追加で機器を持たなくていい
    - 無音/焦点固定のために StageCameraHD2 購入
  - Cons
    - バッテリーがすぐなくなる
    - 4年弱前の機種じゃきつい（機種変予定）
- スマフォホルダ・ケーブル
  - MBPの横に固定
  - スマフォの置き場に悩まない(机がなくていい)
  - レンズの前を塞がない = 固定焦点が狂わない
  - スマフォのバッテリー切れ対策

---

@snap[west]
## 道具(ソフトウェア)
@snapend

---
### 道具(ソフトウェア)

@ul[list](false)
- macOS (AirDrop / スクリーンショット)
- ATOK
  - 走り書きの強い味方
- Visual Studio Code エディタ
  - Backspace++ / Japanese Word Handler / join-line / Zenkaku
  - Markdown All In One / vscode-memo-life-for-you
  - *クリップボード内の文章を加工しつつ貼り付ける機能を探しています*
@ulend

---
### 道具(ソフトウェア) (cont.)

@ul[list](false)
- Firefox ブラウザ
  - Copy as Markdown - 開いたブラウザのタイトルとURLをコピー
  - Multi-Account Containers - 複数AWSアカウントも同時に
  - Format Link - embedly形式でのURLコピーなど
- レベル補正 -> Affinity Photo / PS
- 切り抜き/サイズ変更 -> Skitch / 手製Automator
- pngquant (PNG Reducer)
@ulend

---
### embedly

@snap[west]
@ul[list](false)
- [WordPressの記事でも手軽にリンクをカード型にデザインできるEmbedlyを試してみた ｜ DevelopersIO](https://dev.classmethod.jp/tool/embedly-with-wordpress/)
- [Embedly のカード埋め込み HTML を FormatLink で手軽に生成する ｜ DevelopersIO](https://dev.classmethod.jp/blog/201904-use-embedly-easier-with-formatlink/)
@ulend
@snapend

---
### エディタ・ブラウザ

@snap[west]
（デモ）
@snapend

Note:
- re:Invent 2018 テンプレート
- 書きかけブログ1
- 書きかけブログ2
- 完成ブログ
---

@snap[west]
## 書き方
@snapend

---?image=assets/img/Untitled.png&position=center&size=60%
### 目標

---
### 執筆の流れ

@ul[list](false)
- ネタを決める
- 必要な情報をあつめる（一次情報、やってみる、ぐぐる）
- タイトルと概要説明を仮決めする
- 本文を書く（Markdown）貼る画像の場所や内容も考える
- 貼る画像を用意する
- （必要に応じて）アイキャッチ作る
- DevIOに画像アップロード、画像URLを取得
- Markdownの本文に画像URLをはめ込む
- プレビュー、推敲・校正（表現や漢字の量、誤字脱字）
- 公開
- 公開状態で読み返す、必要に応じて修正
@ulend

---

### 本文の構造：やってみた系記事

@ul[list](false)
- 序文：なんの記事か、これを読むと何が出来るか
  - 注意点がある場合は短くにおわせておく
  - あまり長くしない (PC 1画面に収まる程度)
  - 一次資料のリンク先
- とりあえず動かす/動かした画面や結果の提示
- 実際の手順（長くなりがち）
- この機能の背景を考察
  - なぜこれが要るのか、どういう時にうれしいのか
- 注意点：これをすることで/しないことで発生する不利益など
@ulend

---

### 本文の構造：やってみた系記事 (cont.)

@ul[list](false)
- 序盤で注意を引く、続きを読んでもらう
- 「1画面全てが文章」とならないようにする
  - 画像や表、箇条書きなどがはいるように
- リンクは使い分ける
  - リンク付きテキスト
  - embedly
  - Wordpressのブログカードはバランスをみて使用
- 適度に脚注をいれる
- 適度に ~~ネタ~~ アイスブレイクを仕込む
@ulend

---

### 気をつけていること

@ul[list](false)
- 再現性・実効性があること（汎用性は優先度ひくめ）
  - 同じ事をするのに一番妥当でシンプルな方法を検討
- 誰も悲しまないこと
  - 誰かの功績を否定 or 横取りするような内容は避ける
  - 法的妥当性（著作権とか）も考慮
- 読むひとに伝えたい何かがあること
@ulend

---

@snap[midpoint]
![logo](assets/img/cm_logo_black.png)
@snapend
