## Unityの仕様に関する不具合

-[目次へ](./)

### 日本語がUnity Editor上で文字化けする

スクリプトの作成時になぜか文字コードが「Shift-JIS」になることによる不具合。恐らくバグ。好ましくはUTF-8Nにしたい。

[このページ](https://github.com/sharkattack51/GarageKit_for_Unity/blob/master/UnityProject/Assets/__ProjectName__/Editor/AssetPostprocessUTF8Encode.cs)のスクリプトをコピーしてEditorフォルダに入れるとスクリプト生成時にUTF-8Nにしてくれる。

### スクリプトが更新されない

スクリプトを編集する度にコンパイルが走るのがうっとうしい場合、
「Edit」→「Prefernces」の「Auto Refresh」のチェックを外すと都度コンパイルしないようになる。

スクリプトを編集してもエディタに反映されていないように見える場合、これが原因の可能性がある。

一方、これにチェックをつけているとスクリプトは自動更新されない。

これにチェックをつけずに、「Ctrl + R」で任意のタイミングのみにコンパイルすることもできる。ただ、「Ctrl + R」のあとしばらく経ってからリフレッシュされるため、ちょっと変な感じがする。

また、自動更新しない場合でもプレイを実行しようとするとリフレッシュのような動作が入るが、ここでは自動更新は行われていない。紛らわしい。

Auto Refreshなしを試そうかと思ったが、リフレッシュに似た動作がちょくちょく起こるのにリフレッシュされない、Ctrl+Rを受け付けていない場合があるなど、とにかく紛らわしい挙動が多いので諦めた。

### Visual Studio Editor Package version X.Y.Z is available...という警告が出る

[このページ](https://baba-s.hatenablog.com/entry/2021/07/14/180000)を参照。

「Package Manager」→「In Project」→「Visual Studio」→「Upgrade to X.Y.Z」を押す。

プロジェクトごとに実行する必要がある。

