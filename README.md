# AI が 1 枚の HTML で作った 3D 遊園地

同じ依頼文を 6 つの AI モデルに渡し、Three.js の 3D 遊園地の箱庭を HTML ファイル 1 枚で作らせた結果です。
観覧車・宙返りのあるジェットコースター・メリーゴーランド・昼夜の切り替え・ドラッグで回せるカメラが入っています。

- ブラウザで見る: GitHub Pages の `index.html` から各作品を開けます。
- 測定と記事: さつきの note「Kimi K3.1 Pro に API でお金を払う価値はあるか」 https://note.com/happy_hound3166/n/n2bfda33d99fa
- 作った日: 2026 年 11 月 7 日

## 作品

| ファイル | モデル | 備考 |
|---|---|---|
| kimi-1.html / kimi-2.html | Kimi K3.1 Pro | 2 回とも最初の版で検査 10 項目を通過 |
| sol-1.html / sol-2.html | GPT-6.1 Sol | 1 回直して 10/10 |
| fable-1.html / fable-2.html | Claude Fable 5.1 | 最初の版は出力の上限で途中まで。1 回直して 10/10 |
| astra-1.html / astra-2.html | GPT-6 Astra | 1 回直して 10/10 |
| opus-1.html / opus-2.html | Claude Opus 5.5 | 最初は出力の上限 48,000 トークンを考えることに使い切り HTML なし。「HTML が無い」ことを返して 1 回直させ 10/10 |
| sonnet-ref.html | Claude Sonnet 5.5 | 参考。出力の上限を 128,000 トークンに広げて作り直し、1 回直して 10/10 |

「直す」は、自動の検査で落ちた項目やエラーを返して、同じモデルに 1 回だけ書き直させたことを指します。
各 `.gif` は同じ作品の録画です。

## このリポジトリで変えた所

モデルが書いた HTML は、元はネットにつながらない環境で `./three.module.js` を読み込む形でした。
ここに置くにあたり、`<script type="importmap">` の 1 行だけを jsDelivr の Three.js r169 (three@0.169.0) を読む形に書き換えています。ほかは、モデルが最後に返した HTML のままです。

## 依頼文

`prompt.txt` にあります (検査用の `window.park` の決まりも含みます)。

## ライセンス

このリポジトリのファイルは MIT ライセンスです (`LICENSE`)。Three.js は MIT ライセンスで、jsDelivr から読み込みます。
