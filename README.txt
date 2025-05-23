Gambling プロジェクト README

【プロジェクト概要】
プレイヤーが様々なギャンブルゲームで借金を返済するシミュレーションを提供する Flask + Flask-SocketIO アプリケーション。

【前提条件】
・Python 3.13.3
・Flask 2.3.0
・Flask-SocketIO 5.3.2
・Flask-Session 0.8.0
・gevent または eventlet
・requirements.txt に記載のパッケージ

【セットアップ手順】
1. リポジトリをクローン
   git clone <リポジトリURL>
   cd Gambling
2. 仮想環境を作成・有効化
   python -m venv venv
   source venv/bin/activate  # macOS/Linux
   venv\Scripts\activate     # Windows
3. 依存パッケージをインストール
   pip install -r requirements.txt

【実行方法】
- 開発サーバ：
  export FLASK_APP=app.py      （Windows: set FLASK_APP=app.py）
  flask run
- SocketIO を利用した起動：
  python app.py
-ブラウザ上で【127.0.0.1:9000】を検索

【ディレクトリ構成】
Gambling/
├─ app.py
├─ config.py
├─ extensions.py
├─ package-list.txt
├─ games/
│   ├─ chohan.py
│   ├─ highlow.py
│   ├─ scratch.py
│   ├─ fx.py
│   └─ poker.py
├─ templates/
│   ├─ chohan/
│   ├─ highlow/
│   ├─ scratch/
│   ├─ fx/
│   ├─ poker/
│   └─ common テンプレート
├─ static/
│   ├─ css/style.css
│   ├─ js/
│   │   ├─ socket.io.js
│   │   └─ audio.js
│   ├─ img/（status, dice, card, scratch, chart, gameover）
│   └─ audio/（bgm, sfx）
└─ README.txt

【セッション管理】
Flask-Session を使用し、サーバーサイドに保存
キー: money, debt, luck, difficulty, inventory

【補足】
- コーディングおよび mp3 生成に生成AIを活用
- 画像ファイルは自作
- ER図・画面遷移図は別途資料（発表資料）を参照
