## Tips - 典型的な作り方 - ライティング（基礎）

-[Tipsへ](./../../)

### ライティング設定の作成

「Window」→「Rendering」→「Lighting」でウィンドウを開き、「New Lighting Setting」でライティング設定オブジェクトを新規作成する。新規作成したオブジェクトがシーンのライティング設定になる。

ライティング設定オブジェクトは、シーンフォルダ内に「SceneSettings」フォルダを作り、そこに入れるとよい。他に、カメラプロファイルなどのファイルを入れる。

### Skybox

Skyboxの設定は、シーンのライティング設定を開き、「Environment」→「Skybox Material」で設定する。

Skyboxは背景を決めるだけでなく、環境光にも利用される。

Skybox自体は、（一般的なものは）ボックス状に配置される単なる6枚の画像で、ライトなどの設定は含まない。

ライティング設定の反映は、Skyboxの色の平均などが使用されていると思われる。また、リフレクションプローブを設定しない場合、金属表面にはSkyboxが映る。


### ライトマップをベイクする

ライトマップのベイクというのは、固定された光源・物体間の光の当たり方をあらかじめ計算すること。

これを行うと、シーン上の各メッシュ・各ピクセルに対して光の当たり方を計算したマップが作成される。

手順としては、「Rendering」→「Lighting」ウィンドウを開き、「Baked Lightmaps」タブをクリックして「Generate Lighting」をクリックする。

ただし、通常の設定でこれを実行するとものすごく時間がかかる。これは初期設定で光の計算をかなり細かく行う設定になっているため。

参考ページの「ライトマップを速く焼けるようにする」を参考に、例えば以下のように設定を変更する。

まず、シーンのLightingSettingsがなければ作成する。「Lighting」ウィンドウの「Scene」タブから設定されているLightingSettingsを表示し、

- Lightmap Resolutionを5くらいにする
- Lightmapper以下の、
    - Direct Samplesを1に
    - Indirect Samplesを8に
    - Environment Samplesを8に

する。

最終的な製品のためにしっかり焼くときはこれらを上げる。初期設定では

- Lightmap Resolutionは40
- Lightmapper以下の、
    - Direct Samplesは8
    - Indirect Samplesは128
    - Environment Samplesは256

である。

LighingSettingsは複製できるので、とりあえず焼く用としっかり焼く用のセッティングを作っておくといいかも。


### 参考ページ

[skyboxと環境光を別々に設定する](https://teratail.com/questions/251613)

[Unity ライトマップの焼き方メモ](https://framesynthesis.jp/tech/unity/lighting/)
: かなり分かりやすい。特に「ライトマップを速く焼けるようにする」は必見。
