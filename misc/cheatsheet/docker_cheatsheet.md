# docker_cheatsheet

- [docker_cheatsheet](#docker_cheatsheet)
  - [dockerの始め方](#dockerの始め方)
  - [環境構築例](#環境構築例)
    - [docker imageを取得する方法](#docker-imageを取得する方法)
      - [docker imageを取得する](#docker-imageを取得する)
      - [インストールされているdocker imageの確認](#インストールされているdocker-imageの確認)
      - [新しいコンテナを作成しコマンドを走らせる](#新しいコンテナを作成しコマンドを走らせる)
      - [現在起動中のコンテナを確認する](#現在起動中のコンテナを確認する)
      - [現在起動中のコンテナを停止させる](#現在起動中のコンテナを停止させる)
      - [既存のコンテナを稼働させる](#既存のコンテナを稼働させる)
  - [command helps](#command-helps)
    - [docker pull](#docker-pull)
    - [docker images](#docker-images)
    - [docker run](#docker-run)
    - [docker ps](#docker-ps)
    - [docker attach](#docker-attach)
    - [docker exec](#docker-exec)
    - [docker stop](#docker-stop)
    - [docker start](#docker-start)


## dockerの始め方

## 環境構築例

### docker imageを取得する方法

#### docker imageを取得する
```
docker pull ubuntu:16.04
```

#### インストールされているdocker imageの確認
```
docker images
```

#### 新しいコンテナを作成しコマンドを走らせる

iオプションとtオプションを同時につけることによって操作可能となる

```
docker run -it -d --name my-ubuntu ubuntu:16.04
docker run -d --name my-ubuntu ubuntu:16.04
```

#### 現在起動中のコンテナを確認する
```
docker ps
```

#### 現在起動中のコンテナを停止させる
```
docker stop {CONTAINER NAME}
```

#### 既存のコンテナを稼働させる
```
docker stop {CONTAINER NAME}
```

## command helps

### docker pull
```
Usage:	docker pull [OPTIONS] NAME[:TAG|@DIGEST]

Pull an image or a repository from a registry

Options:
  -a, --all-tags                Download all tagged images in the repository
      --disable-content-trust   Skip image verification (default true)
      --platform string         Set platform if server is multi-platform capable
  -q, --quiet                   Suppress verbose output
```

### docker images
```
Usage:	docker images [OPTIONS] [REPOSITORY[:TAG]]

List images

Options:
  -a, --all             Show all images (default hides intermediate images)
      --digests         Show digests
  -f, --filter filter   Filter output based on conditions provided
      --format string   Pretty-print images using a Go template
      --no-trunc        Don't truncate output
  -q, --quiet           Only show numeric IDs
```

### docker run
```
Usage:	docker run [OPTIONS] IMAGE [COMMAND] [ARG...]

Run a command in a new container

Options:
（多いので一部抜粋）
-i, --interactive                    Keep STDIN open even if not attached
-t, --tty                            Allocate a pseudo-TTY
-d, --detach                         Run container in background and print container ID
--name string                    Assign a name to the container
```


### docker ps
```
Usage:	docker ps [OPTIONS]

List containers

Options:
  -a, --all             Show all containers (default shows just running)
  -f, --filter filter   Filter output based on conditions provided
      --format string   Pretty-print containers using a Go template
  -n, --last int        Show n last created containers (includes all states) (default -1)
  -l, --latest          Show the latest created container (includes all states)
      --no-trunc        Don't truncate output
  -q, --quiet           Only display numeric IDs
  -s, --size            Display total file sizes
```


### docker attach
```
Usage:	docker attach [OPTIONS] CONTAINER

Attach local standard input, output, and error streams to a running container

Options:
      --detach-keys string   Override the key sequence for detaching a container
      --no-stdin             Do not attach STDIN
      --sig-proxy            Proxy all received signals to the process (default true)
```

### docker exec
```
Usage:	docker exec [OPTIONS] CONTAINER COMMAND [ARG...]

Run a command in a running container

Options:
  -d, --detach               Detached mode: run command in the background
      --detach-keys string   Override the key sequence for detaching a container
  -e, --env list             Set environment variables
  -i, --interactive          Keep STDIN open even if not attached
      --privileged           Give extended privileges to the command
  -t, --tty                  Allocate a pseudo-TTY
  -u, --user string          Username or UID (format: <name|uid>[:<group|gid>])
  -w, --workdir string       Working directory inside the container
```

### docker stop

```
Usage:	docker stop [OPTIONS] CONTAINER [CONTAINER...]

Stop one or more running containers

Options:
  -t, --time int   Seconds to wait for stop before killing it (default 10)
```

### docker start
```
Usage:	docker start [OPTIONS] CONTAINER [CONTAINER...]

Start one or more stopped containers

Options:
  -a, --attach                  Attach STDOUT/STDERR and forward signals
      --checkpoint string       Restore from this checkpoint
      --checkpoint-dir string   Use a custom checkpoint storage directory
      --detach-keys string      Override the key sequence for detaching a container
  -i, --interactive             Attach container's STDIN
```

作成済みで停止中のコンテナを起動させます。
「a」オプションでコンテナの出力を表示させます。
結果を垂れ流して、監視するときとかに使うのかな？ちょっとよく分かってないです。
「i」オプションでコンテナの標準入力に装着し、相互モードとなります。
通常のターミナルのように扱えます。

```
docker start -i {CONTAINER NAME}
```

これはよく使います。



