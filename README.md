# セットアップスクリプト

## 手順

以下のコマンドを実行

```powershell
# Powershell
Invoke-WebRequest -Uri "https://raw.githubusercontent.com/Kiikurage/setup/refs/heads/master/configuration.dsc.yml" -OutFile "$env:TEMP\config.yml"; winget configure "$env:TEMP\config.yml"
```

## TODO

今後自動化した項目

- JetBrains ToolBoxからRiderをインストール
- PowerToys設定
    - すべてのモジュールを一旦無効化
    - Keyboard Managerのショートカット再マップ
        - `Win+Space` を `Alt+チルダ` へ
