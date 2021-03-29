# dockerのチュートリアルをなぞる

- [dockerのチュートリアルをなぞる](#dockerのチュートリアルをなぞる)
  - [dockerの始め方](#dockerの始め方)
    - [dockerのインストール](#dockerのインストール)
    - [dockerのチュートリアルに沿う](#dockerのチュートリアルに沿う)
      - [コンテナとは何か？](#コンテナとは何か)
      - [コンテナのイメージとは何か？](#コンテナのイメージとは何か)
      - [sample application](#sample-application)
      - [アプリケーションコンテナの起動](#アプリケーションコンテナの起動)


## dockerの始め方

[https://docs.docker.com/get-started/](https://docs.docker.com/get-started/)

### dockerのインストール

[https://www.docker.com](https://www.docker.com)

詳細は割愛

インストール後、次に進みます。

### dockerのチュートリアルに沿う

terminalなどで、下記コマンドを実行します。

```
docker run -d -p 80:80 docker/getting-started
You’ll notice a few flags being used. Here’s some more info on them:

-d - run the container in detached mode (in the background)
-p 80:80 - map port 80 of the host to port 80 in the container
docker/getting-started - the image to use
```

dオプションをつけることで、コンテナをバックグラウンドで実行できます。
pオプションをつけ引数を指定することで、ホストのポート80番をコンテナのポート80番に繋げられます。

```
Tip

You can combine single character flags to shorten the full command. As an example, the command above could be written as:

docker run -dp 80:80 docker/getting-started
```

1文字のフラグはコマンドの短縮のために組み合わせることができます。
「-d -p」を「-dp」と書き換えて、短縮できてますね！


#### コンテナとは何か？

```
What is a container?

Now that you’ve run a container, what is a container? Simply put, a container is simply another process on your machine that has been isolated from all other processes on the host machine. That isolation leverages kernel namespaces and cgroups, features that have been in Linux for a long time. Docker has worked to make these capabilities approachable and easy to use.
```

前項のコマンドにより、コンテナが実行中となっています。

そこで、コンテナとは何か？

- 簡単にいうと、コンテナとは、ホストマシン上のすべての他のプロセスから隔離された、自分のマシン上の別のプロセスです。
- この隔離は「kernel namespaces」と「cgroups」を最大限に利用したもので、Linuxには昔から備わっているものです。
- Dockerはこれらの機能を親しみやすく、簡単に使えるように努力してきた。

Linuxに昔から備わっている「kernel namespaces」と「cgroups」というもので成り立っているんですね。Dockerはこの機能を容易に使えるように私達に提供してくれているということですね。

使わせていただくしかない！

#### コンテナのイメージとは何か？

```
What is a container image?
When running a container, it uses an isolated filesystem. This custom filesystem is provided by a container image. Since the image contains the container’s filesystem, it must contain everything needed to run an application - all dependencies, configuration, scripts, binaries, etc. The image also contains other configuration for the container, such as environment variables, a default command to run, and other metadata.
```
コンテナを実行するときには、孤立されたファイルシステムが使われます。
このカスタマイズされたファイルシステムはコンテナイメージから提供されます。

イメージにはコンテナのファイルシステムが含まれているため、アプリケーションを実行するために必要なすべてのものが含まれていなければなりません。

- すべての依存関係
- 設定ファイル
- スクリプト
- バイナリ
- その他

また、イメージには、環境変数、実行するための標準コマンド、他の拡張データのような、コンテナの他の設定も含まれています。

#### sample application

tutorialsの案内に従い、appフォルダをローカルに持ってきます。

その後、指定された内容のDockerファイルを作成し、以下のコマンドを実行します。

```
docker build -t getting-started .
```

このコマンドにより、Dockerfileを基にした新しいコンテナイメージが生成されます。

- イメージがダウンロードされる
- アプリケーションをコピーする
- yarnを使い、アプリケーションの依存関係をインストールする
- CMD命令でこのイメージからコンテナを立ち上げたときに実行されるコマンドを指定する

-tフラグでイメージにタグをつけることができる。人間にとって理解しやすい名前をつけて管理するもの。「getting-started」という名前をつけたのでコンテナを立ち上げる際にそのイメージを参照できます。

コマンドの最後の「.」は、DockerにDockerfileを現在のディレクトリの中から探すように指示します。


#### アプリケーションコンテナの起動

イメージができたら「docker run」コマンドを使ってアプリケーションを実行してみます。

```
docker run -dp 3000:3000 getting-started
```

dオプションでバックグラウンドで起動させます。
pオプションでマッピングするポートを指定します。

数秒後、ブラウザで「http://localhost:3000」を開くと、アプリケーションが表示されるはずです。



