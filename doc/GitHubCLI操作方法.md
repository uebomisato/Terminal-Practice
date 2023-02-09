## GitHubCLI\_操作方法

### ▼ 初期設定

1. `gh auth login`コマンドを実行すると、
   「GitHub.com」か「GitHub Enterprise Server」どちらにするか選択する必要があるので、「GitHub.com」を選択。
   `zsh
? What account do you want to log into? GitHub.com
`

2. Git に使うプロトコルを選択する。

   ```zsh
   ? What is your preferred protocol for Git operations? SSH
   ```

3. 端末上の SSH key を GitHub にアップロードするかの確認がある。(既に key を登録している場合は Skip)

   ```zsh
   ? Upload your SSH public key to your GitHub account? /Users/misato/.ssh/uebomisato-GitHub.pub
   ```

4. SSH Key の名前を設定する。

   ```zsh
   ? Title for your SSH key: misato
   ```

5. 認証をブラウザ経由で行うかどうか確認があるので、`Paste an authentication token`を選択。

   ```zsh
   ? How would you like to authenticate GitHub CLI? Paste an authentication token
   ```

6. https://github.com/settings/tokens へ行き、repo と read:org の権限を付与したアクセストークンを作成する。

   ```zsh
   Tip: you can generate a Personal Access Token here https://github.com/settings/tokens
   The minimum required scopes are 'repo', 'read:org', 'admin:public_key'.
   ```

7. 作成したアクセストークンを貼り付ければ、認証が完了する。
   ```zsh
   ? Paste your authentication token: ****************************************
   ✓ Configured git protocol
   ✓ Logged in as uebomisato
   ```

### ▼ ログイン関係

- ログイン
  `gh auth login`
- ログアウト
  `gh auth logout`
- 現在ログインしているアカウントの情報や設定ファイルの確認
  `gh auth status`

### ▼ リポジトリ関係

- クローン
  `gh repo clone [リポジトリ名]`
- 新規作成
  `gh repo create [リポジトリ名] [フラグ]`
  - `--add-readme` : README を作成する
  - `--private` : プライベートリポジトリを作成
  - `--public` : パブリックリポジトリを作成
- 削除
  - `gh repo delete [リポジトリ名]`

### ▼ コミット・プッシュ

- 変更ファイルをadd　(ステージエリアに乗せる)
  `git add .`
- コミット
  `git commit -m "ここにコメント"`
- プッシュ
  `git push origin [ブランチ名]`
- 追加したファイルをステージエリアから戻す
  `git reset`