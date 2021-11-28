## アセットの使い方 - 3Dモデル(ツール) - UModeler

-[アセットの使い方へ](./../)

### 概要

\$137.5で販売。（2021/11時点）

- [公式ドキュメント](https://umodeler.github.io/index.html)

### 導入

「Tools」→「UModeler」→「Create New UModeler」で「UModelerオブジェクト」を生成する。

すると、「UModeler」「Mesh Filter」「Mesh Renderer」「Mesh Collider」が割り当てられたオブジェクトが生成される。

このうち、「Mesh Filter」「Mesh Renderer」「Mesh Collider」の役割は通常のGameObjectと同じ。

[「Mesh Filter」はGameObjectが参照するメッシュを、「Mesh Renderer」はマテリアルなどを保持している。](./../../tips/component/mesh.md)

UModelerで編集するのは、主にMesh Filterが参照しているメッシュである。また、マテリアル割り当てではMesh Rendererの値へも影響を与える。

作成したメッシュは、デフォルトではtripoligon / UModeler / meshassets下に保存されていく。UModelerのフォルダにあるのが気持ち悪いので、
「Umxxxxx(Mesh Filter)」という名前のコンポーネントにある「Save As」ボタンで自プロジェクトのフォルダ内に書き出す。

UModelerを開くとツール群が現れるが、ツール群の設定を表すプロパティウィンドウは実は非表示になっている。

UModelerコンポーネント上で右クリックし、「Floating Properties」にチェックをつけるとプロパティウィンドウが出てくる。

作成したUModelerオブジェクトはTransform.positionが0ではないが、気持ち悪いので0にしてから作業を始めること。

### どんな時に使うべきか

小物を作ったり、動くものを作る場合はBlenderの方が良い。

Unity上で位置合わせを行ったり、レンダリング状況をその場で確認したい場合に使うとよい。
3Dカーソルの座標を決め、それをpivotにするという操作が出来るので、pivotの設定が楽。

床、壁、天井など、家具や小物を置く前の枠を作ったりするのに使うとよい。

### 関連アセットとの比較

Unity上でモデリングするツールとして、公式でProbuilderというモデリングツールとそれを補助するProgridsというツールがある。

当初、これの使用を検討したが、室内マップで壁や天井を作るにあたって座標を厳密に操作するのがかなり難しく、Progridsは長い間「Advanced」（先行トライアル）の期間が続いている。

これを受け、UModelerを検討することとした（アセット自体は既に購入していた）。

### Tips

アイコンタイプのツール表示も可能だが、ここではテキストベースのツール表示で説明する。

#### アセットとして書き出す方法

UModelerにはいくつかの「Export」設定がある。

「objファイル」や「Prefabとして出力」があるが、個人的に一番スッキリする、「余計なもののついていないプレハブ」として出力するには、

「Mesh Filter」コンポーネント内にある「Save As」でMeshだけを書き出し、それをシーンビューにD\&Dで配置し（Mesh FilterとMesh Rendererがアタッチされ、マテリアルはついていないorデフォルトになる）、それらに改めてマテリアルを割り当てることである。

いわゆる「編集可能な状態で保持しておく」には、UModeler用のシーンを作り、そこにUModelerがついたままのGameObjectを保存しておく。
そのシーンはビルド時は除外する。


#### 任意の頂点を厳密な座標に移動

どうも選択した頂点の座標を直接設定する方法はないように思える。

一方、3Dカーソルの位置は数値で設定できる。

3Dカーソルの位置設定
: 「Settings（歯車）」→「Display」→「Cursor Window」にチェックをつけると3Dカーソルの座標を表示するウィンドウが出る。
: 座標を「World Pos」にした上で、このウィンドウの座標に数値を入力すると位置が設定される。

3Dカーソルの位置に頂点を移動
: 頂点を選択した状態だと、メニューに「Move to 3D Cursor」というボタンが出る。
: これをクリックすると3Dカーソルの位置に頂点が移動する。
: ただし、「Settings」でsnapを設定していると、そちらが優先されてしまう。












