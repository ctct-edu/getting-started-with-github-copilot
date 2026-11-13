# 演習09　GitHub Copilot を使い始める

学校の課外活動サイトを題材に、Copilot への質問、コード候補、Agent モード、実装計画、PR の支援を体験します。GitHub と VS Code の基本操作、初歩的なコードの読み方が前提です。

## 始め方

1. 講師から案内された日本語版テンプレートの GitHub ページを開きます。**Use this template** → **Create a new repository** を選び、**Owner** と公開範囲を確認して **Create repository** を選びます。
2. 20秒ほど待って再読み込みします。自分のコピーの **Issues** または **README** に出る案内に合わせて、この資料の同じ番号を開きます。
3. ファイル名、ブランチ名、コード、指定コメントは掲載どおりに入力します。操作後は GitHub 上で次の案内を確認します。

[GitHub Skills の原文 README](https://github.com/skills/getting-started-with-github-copilot) · [教材のライセンス](LICENSE)

## Step 1　Copilot にプロジェクトを紹介してもらう

**Ask** は質問やコードの説明、インライン候補は編集中の補完、インラインチャットは現在のファイルや選択範囲への指示に使えます。

1. Issue の **Open in GitHub Codespaces** から自分の演習コピーの Codespace を作ります。VS Code の **Extensions** で `GitHub Copilot Chat` と `Python` が有効であることを確認します。
2. 上部のチャットアイコンで **Copilot Chat** を開き、**Ask** にします。下の1つ目のプロンプトを使い、プロジェクトの構成と起動方法を尋ねます。
3. **Run and Debug** → **Start Debugging** で起動します。**Ports** でポート `8000` を見つけ、**Open in browser** を選びます。
4. **Terminal** の `+` で新しいターミナルを開き、Windows は `Ctrl+I`、Mac は `Cmd+I` でターミナル内のチャットを開きます。
5. 下の2つ目のプロンプトでブランチの作成と公開を尋ねます。提案されたコマンドを確認して **Run** を選び、左下に `accelerate-with-copilot` が表示されることを確認します。

### Copilot に送るプロンプトの日本語例

1. このプロジェクトの構成を簡潔に説明してください。どうすれば実行できますか。
2. `accelerate-with-copilot` という Git ブランチを作り、GitHub に公開するにはどうすればよいですか。

[このステップの原文](https://github.com/skills/getting-started-with-github-copilot/blob/main/.github/steps/1-step.md)

## Step 2　候補を使って修正し、サンプルデータを作る

近くのコードや開いているファイルは、Copilot が提案を考える手がかりになります。関係するファイルや、期待する動作をプロンプトで具体的に示すこともできます。

1. **Ask** で、同じ活動に二重登録できてしまう原因を尋ねます。
2. `src/app.py` の `signup_for_activity` を開きます。参加者を追加する処理の直前に指定のコメントを書き、改行します。補完候補を読み、内容が合っていれば `Tab` で採用します。
3. `activities` 辞書全体を選び、`Ctrl+I` または `Cmd+I` でインラインチャットを開きます。指定のプロンプトで活動例を追加します。
4. 差分を確認して **Keep** を選び、ブラウザーのサイトに活動が表示されることを確認します。
5. **Source Control** で `app.py` をステージします。**Generate Commit Message** でメッセージ案を作り、内容を確認して **Commit** → **Sync Changes** で送ります。

### 原文のコマンド・入力例

```python
# Validate student is not already signed up
```

### Copilot に送るプロンプトの日本語例

1. #codebase 同じ生徒が同じ活動に2回登録できます。原因はどこにありそうですか。
2. スポーツ、芸術、知的活動をそれぞれ2件ずつ追加してください。

[このステップの原文](https://github.com/skills/getting-started-with-github-copilot/blob/main/.github/steps/2-step.md)

## Step 3　Agent モードで機能を追加する

Agent モードでは、サンプルアプリに必要な編集を複数ファイルにわたって提案できます。変更を採用する前に差分と動作を確認します。

1. チャット下部で **Agent** に切り替えます。必要に応じて `src/static/app.js`、`src/static/index.html`、`src/static/styles.css` をチャットに追加します。
2. 1つ目のプロンプトで、活動カードに参加者の一覧を追加します。サイトと差分を確認し、期待どおりなら **Keep** を選びます。
3. **Tools** で使用できる機能を確認します。2つ目のプロンプトで、参加者を取り消すためのボタンを追加します。サイトで操作し、差分を確認します。
4. 3つ目のプロンプトで、登録後の表示が再読み込みなしでは更新されない問題の修正を依頼します。登録の流れを試してから、`accelerate-with-copilot` にコミットしてプッシュします。

### Copilot に送るプロンプトの日本語例

1. 活動カードに参加者欄を追加してください。登録済みの参加者を箇条書きで表示し、見た目も整えてください。
2. #codebase 各参加者の横に削除アイコンを追加し、箇条書きの記号は表示しないでください。クリックすると、その参加者の活動登録を取り消すようにしてください。
3. 参加者を登録したあと、ページを再読み込みしないと活動カードに反映されません。この動作を修正してください。

[このステップの原文](https://github.com/skills/getting-started-with-github-copilot/blob/main/.github/steps/3-step.md)

## Step 4　Plan モードでテストの実装を計画する

1. **Copilot Chat** を **Plan** に切り替え、FastAPI のバックエンドテストを計画するプロンプトを送ります。
2. 質問があれば回答します。追加の指示で、テストの準備・実行・検証を分ける AAA パターンと `pytest` の利用を指定します。
3. 計画を読み、妥当なら **Start implementation** を選びます。ツールの実行確認が表示されたら、内容がこの演習のテスト実装に必要か確認して判断します。
4. 差分を読み、テストが成功することを確認します。`accelerate-with-copilot` にコミットしてプッシュします。

### Copilot に送るプロンプトの日本語例

1. 別の `tests` ディレクトリに FastAPI バックエンドのテストを追加する計画を立ててください。
2. テストの構成に AAA（Arrange・Act・Assert）パターンを使ってください。
3. `pytest` を使い、`requirements.txt` に追加してください。

[このステップの原文](https://github.com/skills/getting-started-with-github-copilot/blob/main/.github/steps/4-step.md)

## Step 5　プルリクエストに Copilot を使う

1. GitHub で新しい PR を作成します。**base** は `main`、**compare** は `accelerate-with-copilot`、タイトルは `Improve student activity registration system` です。
2. 任意で、説明欄のツールバーにある Copilot の **Summary** を選び、要約を確認します。
3. 任意で、**Reviewers** の Copilot の横にある **Request** を選び、レビューコメントを確認します。利用できない場合は手順2・3を省略できます。
4. **Merge pull request** で変更を取り込み、Issue に表示される完了案内を確認します。

[このステップの原文](https://github.com/skills/getting-started-with-github-copilot/blob/main/.github/steps/5-step.md)

## 振り返り

チャットでプロジェクトを理解し、補完候補で修正し、Agent と Plan の各モードで機能追加やテストを進めました。PR に変更をまとめ、利用できる場合は要約・レビューも試しました。

[このステップの原文](https://github.com/skills/getting-started-with-github-copilot/blob/main/.github/steps/x-review.md)
