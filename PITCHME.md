第11回このサービスは俺に聞け勉強会

# QUIC篇

---

### NOTICE

- 付け焼き刃知識で話してます

---

### Goal

飲み屋で「@color[darkorange](QUICって何)」と聞かれたときに  
適切なウンチクを語れるようになること

---

### Agenda

- QUIC is 何
- HTTP/3 is 何
- 詳解 HTTP/3

---

## QUIC is 何

---

### gQUIC vs iQUIC

- gQUIC (Google QUIC) = @color[darkorange](Google) が始めた実証プロトコル
  - "Quick UDP Internet Connections"
  - 独自の暗号化機能と HTTP の機能を含む
  - 現在 Chrome に実装されているのはこちら
- iQUIC (IETF-QUIC) = @color[darkorange](IETF) が標準化をすすめているもの
  - "A UDP-Based Multiplexed and Secure Transport"
  - SPDY と HTTP/2 の関係みたいな
  - 暗号化機構 = TLS1.3
  - HTTP 部分を「HTTP over QUIC ( @color[darkorange](HTTP/3) )」として切り出す（後述）
  - '19/07 リリース予定

以下、明言ない限り @color[darkorange](QUIC = iQUIC) とします

---

### gQUIC

- 2013年の Chrome vwe.29 より実験開始
- '17/08時点で
  - Googleから流れる全トラフィックの 42.1%
  - インターネット全体だと 2.6〜9.1%

[\[1801.05168\] A First Look at QUIC in the Wild](https://arxiv.org/abs/1801.05168)

---

### TCP vs UDP

- TCP ( HTTP/1.1, HTTP/2 )
  - 「TCP(3 way) + TLS でハンドシェイクが遅い・・・」
  - 「TCP 使わなければいいんじゃね？」 @fa[lightbulb-o fa-orange] （ﾋﾟｺｰﾝ
- QUIC
  - UDP の上にフロー制御やセッションの概念を導入
  - TLS1.3 前提の軽いハンドシェイク

---

### UDP で良かった

- セッション維持したままローミングできるかも！
  - QUIC 独自のコネクション ID で維持
  - Mosh ライク
- パケット到着順に縛られない！
  - 遅いストリームにブロックされない
- 世にある大量の NW 機器も UDP には対応してる

---

### UDP なので・・・

- TCP ほど OS 側が最適化されていない、HW支援もない
  - CPU利用率が上がる可能性
- 世の NW 機器は UDP だと思って通信する
  - セッションテーブルの保持期間問題
- 「UDP は DNS と NTP 以外許可しません」😇
- ALB,NLB,CloudFront「・・・」😇
  - Global Accelerator「😏」

※ 時間が解決してくれることに期待 ※

---

### UDPなのでAMP攻撃が気になります

- [QUICの仕様におけるアンプ攻撃対策 - Qiita](https://qiita.com/flano_yuki/items/5a94fe91b98df98d54d0)

> サーバ側で届いたパケットの送信元IPが正しいか確証が得られてない段階では、クライアントは1200オクテット以上のパケットしか送信してはいけません

- Address Validation
- Path Validation

---

## HTTP/3 is 何

---

### HTTP/3 ( HTTP over QUIC )

- HTTP/2 をベースに QUIC に最適化させたもの
- HTTP/2 のヘッダ圧縮 (HPACK) は QUIC で動かない
  - パケット到着順が保証されないから
  - HTTP/3は @color[darkorange](QPACK) 方式でヘッダを圧縮する
- HTTP/3 は TLS1.3(以上)が前提
  - TLS1.2 以下は切り捨て（暗号強度、0-RTT etc.）
  - S なし HTTP は @color[darkorange](ありません)

---

### ○○ over QUIC

> HTTP 以外のプロトコルを QUIC を使って通信するための対応は、QUIC のバージョン1が実際にリリースされた後に行われるよう延期されました。

---

## 詳解 HTTP/3

---

### 詳解 HTTP/3

ここまで説明した内容は、↓にまとめて書いてあります

- [https://http3-explained.haxx.se/ja/](https://http3-explained.haxx.se/ja/)

---

### その他の参考文献

- またはこれ (ASnoKaze blog)
  - [HTTP over QUICと、その名称について (HTTP3について)](https://asnokaze.hatenablog.com/entry/2018/11/06/025016)
  - [QUICの話 (QUICプロトコルの簡単なまとめ)](https://asnokaze.hatenablog.com/entry/2018/10/31/020215)
  - [QUIC,HTTP/3 の draft-17に関するメモ](https://asnokaze.hatenablog.com/entry/2018/12/23/022715)
  - [QUICの仕様におけるアンプ攻撃対策 - Qiita](https://qiita.com/flano_yuki/items/5a94fe91b98df98d54d0)
- その前にこれ読むと分かりやすい
  - [QUIC標準化動向 〜2017/7](https://www.slideshare.net/kazuho/quic-20177)
  - [http2解説](https://http2-explained.haxx.se/content/ja/)
- その他
  - [draft-ietf-quic-transport-18](https://datatracker.ietf.org/doc/draft-ietf-quic-transport/)
  - [AWS Global AcceleratorにHTTP over QUICを通す #reinvent](https://dev.classmethod.jp/cloud/forward-quic-through-aws-global-accelerator/)
  - [HTTP/3 Study (発表スライド画像)](https://photos.app.goo.gl/ioc9yqojh3y3ntfp8)

---

## Q&A

---

@snap[midpoint]
![logo](assets/img/cm_logo_black.png)
@snapend
