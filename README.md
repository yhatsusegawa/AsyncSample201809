# 実践! ライブコーディングで覚えるasync/await

https://connpass.com/event/95696/ の勉強会用の async/await のサンプルです。

## サンプル内容

RPGなどのドラマパート(会話シーン)を題材に以下の機能を async/await を用いて実装していきます。
* クリックでのテキスト送り
* ネットワークからのテキスト読み込み
* ネットワークからの画像読み込み
* 会話中の選択肢分岐
* 画像が読み込めないときなどの例外処理
* 通信中のローディング表示
* 画像の逐次読み込み（プリロードせずに必要になったタイミングで非同期に読み込む）
* キャンセル処理を応用した会話のスキップ
* 別スレッドを使った並列処理
* Taskをキャッシュとして使い読み込み済みの画像を再利用する

## 動作環境

以下のUnityバージョンで動作確認をしています
* Unity2018.2.4f1
* Unity2018.2.7f1

サンプル中でUniRxの機能を使用しているため、サンプルを試すには AssetStore から UniRx をインポートしておく必要があります。

また、.Net Framework 4.7.1 の機能を使用しているため https://www.microsoft.com/net/download/thank-you/net471-developer-pack から SDK をダウンロードしてインストールしておく必要があります。

## 本サンプルのコードについて

* 一部のファイル名、クラス名、関数名、変数名に日本語を利用しています。これはライブコーディングでのわかりやすさを意図したものです。IDEの入力補完が効きにくくなるのでプロダクトコードでは英語に統一することをお勧めします
* ネームスペースを使用していません。これはライブコーディング時のタイピング数を減らすためです。プロダクトコードでは適切にネームスペースを切りましょう
* stringやstring[]に対する拡張メソッドがあります。これはライブコーディング時のタイピング数を減らすためです。プリミティブな型に対する拡張メソッドはIDEでの入力補完時に候補に出てきやすいため、不適切な利用をされやすくなります。プロダクトコードでは用途に応じて拡張メソッドをネームスペースに閉じ込めるなど汚染対策をしてください
