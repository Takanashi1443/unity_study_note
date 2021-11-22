## アセットの使い方 - 演出 - Cinemachine

-[アセットの使い方へ](./../)

### 導入

Package Managerからインストール。

「Cinemachine」→「Create Virtual Camera」でシーンに「CinemachineVirtualCamera」が
アタッチされたGameObjectが作成される。

同時に、現在のMainCameraに「CinemachineBrain」がアタッチされ、元々のCameraはCinemachineBrainから制御され、自分では制御できなくなる。

「CinamachineVirtualCamera」が「Cinemachine」で使用するカメラに相当する。

既に存在するカメラをCinemachineVirtualCameraにしたい時は一旦Cameraを無効にして新たにCameraを作成しそれを「MainCamera」タグを設定した上で「CinemachineBrain」をAdd Component、既存のCameraに「CinemachineVirtualCamera」をAddComponent。

### 考え方



### よく使うカメラワーク

完全に固定したい場合（例えばFPSの場合）、「Do Nothing」

プレイヤーに対して3人称視点にするなら

### トラブルシューティング

#### 表示がカクつく

以前、混乱してCinemachineVirtualCameraとCameraを併用（同じGameObjectにアタッチ）してしまっていた。

CinemachineVirtualCameraは既存のMainCameraを自動で動かすための仮想的なカメラであり、Cameraをアタッチしてはいけない。

結果、おそらく更新タイミングのズレのためかカクつきが発生した。

ちなみに、Cinemachineでは更新タイミングは「Smart Update」がデフォルトであり、これは見ている対象の更新タイミング（UpdateかFixedUpdateか）によって自動的に更新タイミングを変更するものである。

とは言え、物理演算をするものはFixedUpdateが基本なので、Character Controllerなどを使用する場合もFixedUpdate内で動かした方が良さそう。



