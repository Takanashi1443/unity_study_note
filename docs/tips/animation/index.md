## Tips - アニメーション

-[Tipsへ](./../)

### 参照アセット

- 人型キャラクターのアニメーションは[Very Animation](./../../assets/3d_character/very_animation/)での制作を基本とする。

### 基本

#### AnimatorとAnimation (Animation Clip)とAnimation ControllerとAvatarの関係

Animatorはコンポーネントで、そこにAnimation ControllerとAvatarを設定する。

Avatarは、モデルのボーン等の情報を記録し、アニメーションの内容をモデルごとの動きに落とし込むためのデータ。

Animation Controllerはアニメーションの制御を行うコンポーネントで、Unity上のエディタで内容を編集する。

Animation Controller内で設定する個々の動きがAnimation（Animation Clipとも。両者は同じ）。

Very Animationは主にAnimation CLipを制作するツール。

#### AnimationClipの命名規則

AnimationClipは、複数のキャラで共通のこともあれば、キャラごとに調節することもある。

ここでは、共通で「Subject\@Action」という名前で表記する。

例えば、Tomというキャラが歩くモーションであれば「Tom\@Walk」といった具合。

複数のキャラで共通の場合は、複数のキャラの総称を使用する。例えば、全キャラで共通のVサインのポーズは「Human\@VSign」という具合。アクションの内容はキャメルケースで記す。


### Tips

- FBXをシーンにD\&DするとAnimatorつき、AnimatorControllerが無い状態でシーン上に生成されるが、その状態でAnimationClipをAnimator上にD\&Dするとそのアニメーションのみが設定されたAnimatorControllerが自動生成される。




### 参考ページ

- [VeryAnimationを使ってオリジナルアニメーションを作る方法](https://styly.cc/ja/tips/unity-saku-animation/)

