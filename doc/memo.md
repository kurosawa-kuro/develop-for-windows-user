ドキュメントを清書しました。

# 下準備
- 付箋とSlackを一時停止します。

# 仮想環境のインストール
- VagrantとVirtualBoxをインストールします。

# Vagrantfileのダウンロード
- 次のURLからVagrantfileのリポジトリをダウンロードします：[https://github.com/kurosawa-kuro/vagrant-ubuntu](https://github.com/kurosawa-kuro/vagrant-ubuntu)

# 仮想環境の起動
- ダウンロードしたリポジトリのディレクトリに移動し、`vagrant up`コマンドを実行して仮想環境を起動します。

```
C:\Users\kuros\Downloads\vagrant-ubuntu-master\vagrant\ubuntu
ls
vagrant up
```

# VagrantとVSCodeの連携
- Remote Explorerを使用して、VagrantとVSCodeを連携させます。

```
vagrant ssh-config

Host vagrant_ubuntu
    HostName 127.0.0.1
    User vagrant
    Port 2222
    UserKnownHostsFile /dev/null
    StrictHostKeyChecking no
    PasswordAuthentication no
    IdentityFile C:/Users/kuros/Downloads/vagrant-ubuntu-master/vagrant/ubuntu/.vagrant/machines/default/virtualbox/private_key
    IdentitiesOnly yes
    LogLevel FATAL
    PubkeyAcceptedKeyTypes +ssh-rsa
    HostKeyAlgorithms +ssh-rsa
```

# VagrantとGitHubの連携
- Gitの設定を行います。

```
pwd
git config --global user.name "My Name"
git config --global user.email "My Mail Address"
```

- Vagrant内でSSHキーを生成します。

```
ssh-keygen -t ed25519
ls /home/vagrant/.ssh/id_ed25519
cat /home/vagrant/.ssh/id_ed25519.pub
```

- GitHubにログインし、「Settings」から「SSH and GPG keys」セクションに移動し、「New SSH key」ボタンをクリックして、生成した公開キーを登録します。

- ローカルで新しいディレクトリを作成し、`git init`コマンドを実行してGitリポジトリを初期化します。
