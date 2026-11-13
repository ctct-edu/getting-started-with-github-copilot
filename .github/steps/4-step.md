## Step 4　Plan モードでテストの実装を計画する

1. **Copilot Chat** を **Plan** に切り替え、FastAPI のバックエンドテストを計画するプロンプトを送ります。
2. 質問があれば回答します。追加の指示で、テストの準備・実行・検証を分ける AAA パターンと `pytest` の利用を指定します。
3. 計画を読み、妥当なら **Start implementation** を選びます。ツールの実行確認が表示されたら、内容がこの演習のテスト実装に必要か確認して判断します。
4. 差分を読み、テストが成功することを確認します。`accelerate-with-copilot` にコミットしてプッシュします。

### Copilot に送るプロンプトの日本語例

1. 別の `tests` ディレクトリに FastAPI バックエンドのテストを追加する計画を立ててください。
2. テストの構成に AAA（Arrange・Act・Assert）パターンを使ってください。
3. `pytest` を使い、`requirements.txt` に追加してください。

### 画面での確認

- Copilot Chat の入力欄付近で **Plan** を選びます。計画の中にテスト用フォルダと `pytest` の追加が含まれることを確認してから **Start implementation** を選びます。
- 完了後は **Explorer** でテストファイルを、**TERMINAL** でテスト結果を、**Source Control** で変更一覧を確認します。

[原文](https://github.com/skills/getting-started-with-github-copilot/blob/main/.github/steps/4-step.md)
