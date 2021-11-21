## アセットの使い方 - 演出 - Cinemachine

-[アセットの使い方へ](./../)

### 導入

Package Managerからインストール。

「Cinemachine」→「Create Virtual Camera」でシーンに「CinemachineVirtualCamera」が
アタッチされたGameObjectが作成される。

同時に、現在のMainCameraに「CinemachineBrain」がアタッチされ、元々のCameraはCinemachineBrainから制御され、自分では制御できなくなる。

「CinamachineVirtualCamera」が「Cinemachine」で使用するカメラに相当する。

既に存在するカメラをCinemachineVirtualCameraにしたい時は一旦Cameraを無効にして新たにCameraを作成しそれを「MainCamera」タグを設定した上で「CinemachineBrain」をAdd Component、既存のCameraに「CinemachineVirtualCamera」をAddComponent。

### よく使うカメラワーク



