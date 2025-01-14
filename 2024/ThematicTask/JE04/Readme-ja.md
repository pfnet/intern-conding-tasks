# JE04 【10日間】汎用原子レベルシミュレータ Matlantis における Web システムの開発・運用就業体験

## コーディングテスト
以下の URL から受験してください。 (URL 省略)

問題は全部で 6 問ありますが、その **全てを解く必要はありません** 。
このテーマでは、以下の 3 問を解いていただきます。
- 1 (非公開の問題)
- 2 (非公開の問題)
- 3 ポーカーの勝率

コーディングテストの回答にあたっては、以下のいずれかの言語を用いて回答してください。
- Python3
- Go
- TypeScript

## テーマ別課題

### 問題
あなたは過去自分で作成したLLMを用いたチャット形式の論文要約サービスをSaaSとして提供しています。
あなたは新機能として要約に使われるLLMをユーザーが所有するデータで追加学習できるようにする新機能（以下、追加学習機能）をリリースすることにしました。

### 前提条件・要件
このサービスはAWSやGCPなどのクラウドサービス上で動作しています。追加学習機能の要件を以下の通り整理しました。

#### フロントエンド
フロントエンドには以下二つの画面を作成します。
* 実行画面: 追加学習処理を開始するための画面。名前の入力欄、学習用データセットのアップロード欄から構成されるフォームが配置されている。
* 一覧画面: 実行中、 完了済みの追加学習処理の名前、 開始時刻、 終了時刻、 ドキュメント数が表示されます。

同一のユーザーで重複した名前を指定することはできません。
一覧画面におけるエポック数はリアルタイムに表示される必要はありませんが、5分に1回程度最新の値が表示される必要があります。

#### バックエンド
バックエンドには追加学習を実行するための機能を追加します。この機能は以下の要件を満たす必要があります。
* 追加学習処理を動かすには1つのGPUが必要です。追加学習処理には少なくとも1時間かかることが分かっています。
* ユーザーは最大10GBまでの学習用データセットをアップロードできます。
* サーバーは追加学習処理を少なくとも2つ以上並列に動かせる必要があります。
* 3日以上動いている追加学習処理は異常な状態と見なして終了させる必要があります。
* バックエンドが受けるHTTPリクエストに対する認証・認可機構に関しては既存のものがあるので新たに開発する必要はありません。
* リクエストの頻度は一定でなく時間帯やSNSでの拡散によって変化することが予想されます。

### 課題内容
あなたがこの新機能の開発に参加する場合に、フロントエンド、バックエンド、インフラのいずれかもしくは複数の分野で、あなたが実装において重要だと思うポイントについてレポートをまとめてください。全ての分野を書く必要はありません。あなたが得意な分野についてまとめてください。

* **実装に必要な具体的なライブラリやサービスが明示されている場合、加点します。**
    * AWSやGCPなどのクラウドサービスをあげていただいても構いません。

* 例として以下のようなポイントがあると思われます。
    * フロントエンド, UX, API設計
        * 大容量の学習用データセットのアップロードをどう設計しますか?
        * アップロードのユーザー体験の改善のためにあなたができることはありますか？
        * 入力された名称のバリデーションをどのように行いますか?
    * バックエンド
        * あなたは追加学習処理をどのように実装しますか?
        * 学習の状況をユーザーが確認するためにはどのような実装が考えられますか？
        * 開発工数や運用コストを削減するためにどのようなマネージドサービスを使うのが効率的ですか？またマネージドサービスを導入するデメリットは何ですか?
        * どのようにテストを実装しますか?
        * セキュリティの観点から注意するべき点はありますか?
    * インフラ
        * 常時高価なGPUをたくさん立ち上げておくのはコストがかかりすぎてしまいます。どのようにオートスケーリングを実装しますか？
        * GPU以外のインフラコストの節約のために何ができますか?
    * 要件
        * ユーザー体験を改善するために追加できる要件はありますか?
        * セキュリティを改善するために追加できる要件はありますか?

上記以外のポイントを書いていただいても問題ありません。また全て満たす必要はありません。**あなたが追加処理機能を実現するにあたって、技術的な観点から重要だと思うこと、自分が大きく貢献できると思うこと**を教えてください。

回答には、新規性を別途主張できるようなアイディアは含めないでください。

### 提出方法
survey.pdf というファイル名で A4 サイズ 2 枚以内の PDF にまとめ、提出してください。
