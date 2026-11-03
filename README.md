# MyTube Organizer — GitHub Pages 公開用サイト

このフォルダには、MyTube Organizer v0.4.4 の紹介ページ、プライバシーポリシー、利用規約を収録しています。**Chrome拡張機能のソースや個人のOAuth情報は含んでいません。**

## 公開前に必ず行うこと

1. `privacy.html` と `terms.html` にある **`【公開前に連絡先メールアドレスを入力】`** を、自分が公開してよい問い合わせ先へ変更する。
2. 文面が現在の拡張機能の実際の仕様と一致するか確認する。将来、データ収集の仕組みを変更した場合も改訂する。
3. サイトは **インターネット全体に公開される**。個人のチャンネル一覧・バックアップJSON・OAuthクライアントの設定・APIキーなどを絶対にサイトのリポジトリへアップロードしない。
4. サイトの公開だけで、Google OAuthの検証・審査に自動合格するわけではない。審査が必要なら案内に従い、ドメイン所有の確認などを行う。

## 一番簡単なGitHub Pages公開方法

1. GitHubでアカウントを用意して、`https://github.com/new` から新しい **Public** リポジトリを作る。
2. リポジトリ名を **`<GitHubユーザー名>.github.io`** にする（例：`exampleuser.github.io`）。この形式だとWebサイトをドメイン直下に設置できる。
3. ZIPを展開して、`index.html`、`privacy.html`、`terms.html`、`styles.css` をリポジトリのルートにアップロード／コミットする。READMEや`.nojekyll`を含めてもよい。
4. リポジトリの **Settings → Pages → Build and deployment → Source: Deploy from a branch**、**Branch: main / (root)** を選び **Save**。
5. 公開URL `https://<GitHubユーザー名>.github.io/` を開き、ページが見えるか確認する。数分かかることがある。
6. 同じドメイン上の次のURLが開けるか確認する。
   - ホームページ：`https://<GitHubユーザー名>.github.io/`
   - プライバシーポリシー：`https://<GitHubユーザー名>.github.io/privacy.html`
   - 利用規約：`https://<GitHubユーザー名>.github.io/terms.html`

## Google Auth Platform の入力例

- **Google Cloud Console → Google Auth Platform → Branding** を開く。
- **App name:** `MyTube Organizer`
- **User support email:** 利用する問い合わせ先のメールアドレス
- **Application homepage:** 公開したトップページのURL
- **Application privacy policy link:** 公開した `privacy.html` のURL
- **Application terms of service link**（表示される場合）：公開した `terms.html` のURL
- **Authorized domains**（入力が必要な場合）：実際の公開ドメインに関するGoogle側の画面案内に従う。
- **Audience** から本番環境への切り替えを試す。審査・所有権確認が必要な場合は、そのガイドに従う。

### Googleがドメイン確認を要求したら

Google Search Console (`https://search.google.com/search-console/`) の **URLプレフィックス** に、公開したルートURL `https://<GitHubユーザー名>.github.io/` を追加する。所有権の確認用にHTMLメタタグが発行された場合は、そのタグを `index.html` の `<head>` 内に貼り付けてサイトを更新する。確認が完了するまでタグは残す。

**注意：** GitHub Pagesなどの共有ホスティングのドメインは、GoogleのOAuth審査に必要な「所有ドメイン」確認で問題になることがある。Google側で認められない場合は、所有する独自ドメインを使用する必要がある。URLや必要項目はGoogle Cloudの表示に従うこと。

## 権限やAPIに関して

- サイト自体はHTML/CSSのみで、Google OAuth認証やトラッキングを行いません。
- Chrome拡張機能は `youtube.readonly` を要求し、登録チャンネルや手動更新の動画情報をGoogleのYouTube Data APIから取得します。
- Chrome拡張機能側は、YouTube API Servicesの利用規約・開発者ポリシーの対象です。Webサイトの作成のみで全ての規約要件を満たすとは限りません。一般公開・審査を行う場合、拡張機能側にプライバシーへの同意導線などが必要になることがあります。

参考：
- https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site
- https://developers.google.com/identity/protocols/oauth2/production-readiness/policy-compliance
- https://developers.google.com/youtube/terms/developer-policies

### 表示サンプルについて

ホームページのフォルダとチャンネルは架空の名称を使用しています。実在の団体・個人を例示したものではありません。
