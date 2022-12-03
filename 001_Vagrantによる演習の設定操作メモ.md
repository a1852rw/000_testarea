# 演習の設定操作メモ
## 操作環境
- Vagrantで構築した環境
- OS：Rockey Linux 9

## コマンド操作
### 起動
- vagrnt up
- vagrant ssh

### スナップショット作成 001
- vagrant snapshot save  savepoint_001
- スナップショットの確認
    - vagrant ssnapshot list
    - 「snapshot_001」が表示されたのでＯＫ

### セキュリティ設定
#### P5 Selinuxが有効であることを確認
- sudo less /etc/selinux/config
    - SELINUX=permissive と表示された = アクセス制御されない = NG
    - Enforcing に変更する
- sudo yum -y install vim
    - vim をインストールして設定を編集
- sudo vim /etc/selinux/config
    - SELINUX=permissive を　SELINUX=Enforcing に手動で書き換え
- sudo reboot now
    - 設定を反映するため再起動
- getenforce
    - Enforcing と表示されたので設定成功

#### P6 設定内容の確認
- 



