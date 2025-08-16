# セットアップスクリプト

## Windows

OSインストール直後、Powershellで以下のコマンドを実行

```powershell
# Powershell
Invoke-WebRequest -Uri "https://raw.githubusercontent.com/Kiikurage/setup/refs/heads/master/configuration.dsc.yml" -OutFile "$env:TEMP\config.yml"; winget configure "$env:TEMP\config.yml"
```

<details>
  <summary>設定内容</summary>

- OSの設定
    - 隠しファイルを表示
    - 拡張子を表示
    - タスクバーの検索ボックスを非表示に
    - タスクバーの「タスクビュー」アイコンを非表示に
    - タスクバーのウィジェットを非表示に
- アプリのインストール
    - 1Password
    - Google Chrome
    - VSCode
    - Visual Studio 2022
    - PowerToys
    - JetBrains Toolbox
    - Steam
    - Epic Games Launcher
- PowerToysの設定
    - いらないモジュールの無効化

- 今後対応したいこと
    - JetBrains ToolBoxからRiderをインストール
    - WSLにzsh/oh-my-zshを導入
    - PowerToys設定
        - Keyboard Managerのショートカット再マップ
            - `Win+Space` を `Alt+チルダ` へ
    - Microsoft IMEの削除

</details>

