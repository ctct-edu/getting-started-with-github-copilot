## Step 1　Copilot にプロジェクトを紹介してもらう

**Ask** は質問やコードの説明、インライン候補は編集中の補完、インラインチャットは現在のファイルや選択範囲への指示に使えます。

1. Issue の **Open in GitHub Codespaces** から自分の演習コピーの Codespace を作ります。VS Code の **Extensions** で `GitHub Copilot Chat` と `Python` が有効であることを確認します。

   [![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/{{full_repo_name}}?quickstart=1)
2. 上部のチャットアイコンで **Copilot Chat** を開き、**Ask** にします。下の1つ目のプロンプトを使い、プロジェクトの構成と起動方法を尋ねます。
3. **Run and Debug** → **Start Debugging** で起動します。**Ports** でポート `8000` を見つけ、**Open in browser** を選びます。
4. **Terminal** の `+` で新しいターミナルを開き、Windows は `Ctrl+I`、Mac は `Cmd+I` でターミナル内のチャットを開きます。
5. 下の2つ目のプロンプトでブランチの作成と公開を尋ねます。提案されたコマンドを確認して **Run** を選び、左下に `accelerate-with-copilot` が表示され、GitHub にも同名のブランチが作成されていることを確認します。

### Copilot に送るプロンプトの日本語例

1. このプロジェクトの構成を簡潔に説明してください。どうすれば実行できますか。

2. `accelerate-with-copilot` という Git ブランチを作り、GitHub に公開するにはどうすればよいですか。

### 画面での確認

- GitHub の演習 Issue を開いたタブを残し、Codespace の **Repository** に自分のユーザー名／演習名が表示されていることを確認して作成します。
- VS Code の左端の四角が並ぶアイコンが **Extensions**、再生ボタンと虫のアイコンが **Run and Debug** です。**Ports** はエディターの下にあります。ポート `8000` の行でブラウザーを開き、サンプルサイトが表示されることを確認します。

[原文](https://github.com/skills/getting-started-with-github-copilot/blob/main/.github/steps/1-step.md)
