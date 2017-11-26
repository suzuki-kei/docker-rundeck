# docker-rundeck

## 概要

以下の構成を docker-compose で作成する.

    * Nginx x 1
    * Rundeck server x 2
    * Rundeck node x 3
    * MySQL x 1

Nginx からは ip_hash で Rundeck server に振り分ける.

## 使い方

(1) SSH 鍵ペアを生成する

    ssh-keygen -t rsa -b 4096 -N '' -C 'rundeck' -f ./volumes/rundeck-server/var/lib/rundeck/.ssh/id_rsa

(2) コンテナを起動する

    docker-compose up -d

(3) ブラウザで Rundeck の Web UI を開く

    http://localhost:10080

(4) プロジェクトを作成する

    任意の名前でプロジェクトを作成する.

(5) ジョブの実行ノードを追加する

    1. プロジェクトメニューの "Project > Edit Nodes..." をクリックする.
    2. "Configura Nodes" をクリックする.
    3. "Add Source+" をクリックする.
    4. "+Directory" をクリックする.
    5. "Directory Path" に "/var/rundeck/resources" を入力し, "Save" をクリックする.

(6) ジョブを追加する

    1. プロジェクトメニューの "Jobs" をクリックする.
    2. "Upload a Job definition..." をクリックする.
    3. job-definitions/hello.yml をアップロードする.

(7) ジョブを実行する

    1. プロジェクトメニューの "Jobs" をクリックする.
    2. "Hello" ジョブを実行する.

