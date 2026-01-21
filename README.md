# 日野市文化財マップ (Hino City Cultural Asset Map)
日野市内の指定文化財を地図上で閲覧できるインタラクティブなWebマップです。 Leaflet.jsを使用し、日野市のオープンデータを可視化しています。文化財の場所、種別、解説を確認することができます。

## 🌐 デモ (Demo)
• 公開URL: [日野市文化財マップ](https://hino-bunkazai-map.web.app/)  
  　
## ✨ 特徴 (Features)
+ 文化財の可視化: 市内の重要文化財、史跡、天然記念物などを地図上にピンで表示。
+ 詳細情報の表示: ピンをクリックすると、文化財の名称、種別、解説文がポップアップ表示されます。
+ クラスタリング機能: 「高幡不動尊」周辺など、ピンが密集している地域では自動的にグループ化（クラスタリング）され、地図が見やすくなっています。
+ 現在地表示: GPS機能を使用し、現在地周辺の文化財を探すことができます。
+ データ分離設計: 地図データは data.geojson として独立しており、データの追加・修正が容易です。  
  　
## 🛠 使用技術 (Tech Stack)
+ HTML5 / CSS3
+ JavaScript (ES6)
+ Leaflet.js (v1.9.4) - 地図描画ライブラリ
+ Leaflet.markercluster - マーカーのクラスタリングプラグイン
+ GeoJSON - 地理空間データのフォーマット
+ Firebase Hosting - 静的ホスティングサービス  
  　
## 📂 ファイル構成 (File Structure)
ソースコードの構成はシンプルに保たれています。  
.  
├── index.html      # メインの地図アプリ（Leafletの読み込みとロジック）  
├── data.geojson    # 文化財のデータファイル（緯度経度、名称、解説など）  
├── firebase.json   # Firebase Hostingの設定ファイル  
├── .gitignore      # Git管理除外設定  
└── README.md       # プロジェクトの説明書（本ファイル）  
  　
## 🚀 ローカルでの実行方法 (Development)
このプロジェクトは外部ファイル（GeoJSON）を読み込むため、ローカルで単にHTMLファイルを開いただけではブラウザのセキュリティ制限（CORS）により動作しない場合があります。以下のいずれかの方法でローカルサーバーを立ち上げて確認してください。  

+ 方法1: Firebase CLIを使用する場合（推奨）  
Firebaseプロジェクトが設定済みの環境であれば、エミュレータを使用できます。  
firebase emulators:start --only hosting  
表示されたローカルURL（例: http://localhost:5000）にアクセスします。  
  　
+ 方法2: VS Code Live Serverなどを使用する場合  
Visual Studio Codeの拡張機能「Live Server」などを利用して index.html を開いてください。  
  　
## 📊 データの更新方法 (Data Update)
文化財データを追加・修正する場合は、index.html を編集する必要はありません。 data.geojson ファイルを以下の形式で編集してください。  
{  
  "type": "Feature",  
  "geometry": {  
    "type": "Point",  
    "coordinates": [経度, 緯度]  // 注意: Leaflet(緯度,経度)とは順序が逆です  
  },  
  "properties": {  
    "name": "文化財の名称",  
    "type": "種別（例：市指定史跡）",  
    "desc": "解説文"  
  }  
}  
  　
## 🌍 データ出典 (Data Source)
本アプリケーションで使用している文化財データは、以下のオープンデータを利用・加工しています。  
• データ元: 日野市指定文化財一覧  
• ライセンス: クリエイティブ・コモンズ 表示 4.0 国際 ライセンス (CC BY 4.0)  
  
• 提供: 日野市 (Hino City)
📜 ライセンス (License)
This project is open source and available under the MIT License.
