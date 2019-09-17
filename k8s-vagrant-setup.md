vagrant
            cat /etc/*release
    sudo設定
        sudo su -
        echo "sysadmin ALL=NOPASSWD: ALL" | EDITOR='tee –a' visudo >/dev/null
    VirtualBox インストール
        リポジトリ鍵追加&インストール
            cd ;cd ./Downloads
            wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- | sudo apt-key add -
            wget -q https://www.virtualbox.org/download/oracle_vbox.asc -O- | sudo apt-key add -
        リポジトリ追加
            sudo add-apt-repository "deb [arch=amd64] http://download.virtualbox.org/virtualbox/debian xenial contrib"
        リポジトリアップデート
            sudo apt update
        ライブラリ追加
            wget http://mirrors.kernel.org/ubuntu/pool/main/libs/libsdl1.2/libsdl1.2debian_1.2.15+dfsg1-3_amd64.deb
            sudo apt install ./libsdl1.2debian_1.2.15+dfsg1-3_amd64.deb
        VirtualBoxインストール
            sudo apt install virtualbox-6.0
    vagrantインストール
        ダウンロード
            wget https://releases.hashicorp.com/vagrant/2.2.5/vagrant_2.2.5_x86_64.deb
        インストール
            sudo apt install ./vagrant_2.2.5_x86_64.deb
        設定
            git clone https://github.com/kenfdev/kubernetes-the-hard-way-vagrant.git
            cd kube*
        起動
            vagrant up
        稼動確認
            vagrant status
