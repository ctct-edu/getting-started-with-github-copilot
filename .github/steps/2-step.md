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

[原文](https://github.com/skills/getting-started-with-github-copilot/blob/main/.github/steps/2-step.md)
