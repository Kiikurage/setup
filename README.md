## 手順

1. Windowsをローカルアカウントで初期化

2. DSCで構成管理

```powershell
# Powershell
winget configure --enable    
winget configure 
```

5. 自動化できていない項目

- 1passwordのログイン
- JetBrains ToolBoxからRiderをインストール
- PowerToys設定
    - すべてのモジュールを一旦無効化
    - Keyboard Managerのショートカット再マップ
        - `Win+Space` を `Alt+チルダ` へ
