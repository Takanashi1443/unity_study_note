## アセットの使い方 - 3Dモデル - Fantastic Nature Pack

-[アセットの使い方へ](./../../)

### サンプルシーンについて

#### カメラが複数ある(Version 1.5)

シーンにカメラが7台あり、最初はCam_01_forestが有効になっている。それ以外のカメラも新ビューで選択すると、どうやら景色を映している。しかし、Cam_01_forestを無効にすればCam_02が映るわけではなく、「No Cameras Rendering」となる。

[カメラが複数台ある](./media/nature_multiple_camera.png)

Cameraやゲームオブジェクトが無効になっているわけでもない。妙なスクリプトがついているわけでもない（UniversalAdditionalCameraData.csはUnity標準）。

[このへん](https://zenn.dev/fuqunaga/articles/c29337f01658f49)も関係ある？

よく見ると「Output」の「Target Display」がそれぞれDisplay1～7になっている。これはマルチディスプレイに対応するためらしい。対戦ゲームとかで使う、デュアルディスプレイなどにそれぞれの画面を表示する機能のよう。今回は関係ない。

Target Displayを全てDisplay1にしたら他のカメラも映すことができ、Beach含む複数を映した場合はGameObjectの順番に関係なくBeachのカメラが描画された。また、複数画面を描画すると非常に動作が重い。

### 雑記

#### 多くがTerrainで配置されている

VillageやHalloweenと異なり、多くの植物系のオブジェクトがTerrainで配置されている。
