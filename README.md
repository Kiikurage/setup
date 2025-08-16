## 手順

1. Windowsをローカルアカウントで初期化

2. WinRMを有効化しリモートコントロールを可能にする

    ```bash
    # PowerShell

    # WinRM(リモートコントロール)の有効化
    winrm quickconfig -force

    # Basic認証を有効化しAnsibleエージェントから接続可能にする
    Set-Item -Path WSMan:localhost\Service\Auth\Basic -Value $true

    # Ansibleからの通信は非SSLなHTTPなのでこれを許可
    Set-Item -Path WSMan:\localhost\Service\AllowUnencrypted -Value $true

    # Ansibleが使用する5985ポートを開放
    netsh advfirewall firewall add rule name="WinRM HTTP" dir=in localport=5985 protocol=TCP action=allow
    ```

3. WSLを初期化

    ```bash
    # PowerShell
    wsl --install
    ```

    ```bash
    # WSL
    mkdir workspace
    cd workspace
    python3 -m venv ansible
    cd ansible
    ./bin/pip install ansible pywinrm
    ```

4. Ansibleを実行

    ```bash
    # WSL
    ANSIBLE_USERNAME="(USERNAME)" ANSIBLE_PASSWORD="(PASSWORD)" ./bin/ansible-playbook -i hosts setup-windows.yml
    ```

### 環境変数

| 環境変数 | 内容 |
| --- | --- |
| `ANSIBLE_USERNAME` | WindowsのUsername
| `ANSIBLE_PASSWORD` | WindowsのPassword |
