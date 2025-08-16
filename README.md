## 手順

1. Windowsをローカルアカウントで初期化

2. DSCで構成管理

```powershell
# Powershell
Invoke-WebRequest -Uri "https://raw.githubusercontent.com/Kiikurage/setup/refs/heads/master/configuration.dsc.yml" -OutFile "$env:TEMP\config.yml"; winget configure "$env:TEMP\config.yml"
```

3. 自動化できていない項目

- 1passwordのログイン
- JetBrains ToolBoxからRiderをインストール
- PowerToys設定
    - すべてのモジュールを一旦無効化
    - Keyboard Managerのショートカット再マップ
        - `Win+Space` を `Alt+チルダ` へ
