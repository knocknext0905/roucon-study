労コンStudy PWA版 v4.0

【構成】
- index.html
- manifest.webmanifest
- service-worker.js
- icons/

【オフライン利用】
PWAのService Workerは file:// では動きません。HTTPSで公開するか、開発時は localhost で起動してください。
一度オンラインで起動すると、アプリ本体・問題データ・アイコンが端末にキャッシュされ、その後はオフラインでも問題演習できます。学習履歴は端末のlocalStorageに保存されます。

【簡単なローカル確認】
このフォルダで Python が使える場合：
  python -m http.server 8000
その後、ブラウザで http://localhost:8000/ を開きます。

【公開】
GitHub Pages / Cloudflare Pages / Netlify 等のHTTPS静的ホスティングに、このフォルダの中身をそのまま配置してください。

【更新】
index.htmlやservice-worker.jsを更新する際は、service-worker.jsの CACHE_NAME も変更すると確実です。


【GitHub Pages 公開用】
1. GitHubで public repository（例: roucon-study）を作成
2. ZIPを展開し、フォルダ内の index.html / manifest.webmanifest / service-worker.js / .nojekyll / icons フォルダをリポジトリ直下へアップロード
3. Settings > Pages > Build and deployment > Source: Deploy from a branch
4. Branch: main、Folder: /(root) を選び Save
5. 公開URL（https://<ユーザー名>.github.io/<リポジトリ名>/）を開く
6. 一度オンライン起動後、Service Workerがアプリ本体をキャッシュし、オフライン利用可能
