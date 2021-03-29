# terminal command cheat sheet

- [terminal command cheat sheet](#terminal-command-cheat-sheet)
	- [基本操作](#基本操作)
	- [出力](#出力)
	- [man](#man)
	- [find](#find)
		- [grep](#grep)

## 基本操作

|操作|動作|
|:-:|:-:|
|ctrl + f|カーソルを前に動かす|
|ctrl + b|カーソルを後ろに動かす|
|ctrl + p|カーソルを上へ動かす|
|ctrl + n|カーソルを下へ動かす|
|ctrl + a|カーソルを行頭へ移動させる|
|ctrl + e|カーソルを行末へ移動させる|
|ctrl + h|後ろの一文字を消す（backspace）|
|ctrl + d|前の一文字を消す（delete）|
|ctrl + c|（何らかのプロセスが動作しているときに）強制終了|
|ctrl + d|接続している環境から抜ける（exit）|



## 出力

```
>
```

## man
コマンドの説明を表示させる

```
man find | col -b > __find_command_manual__.txt
```

## find

```
find: illegal option -- -
usage: find [-H | -L | -P] [-EXdsx] [-f path] path ... [expression]
       find [-H | -L | -P] [-EXdsx] -f path [path ...] [expression]
```

```
find . --name "*.md"
```

### grep

```
find . | grep -irl "filename"
```

```
     -i, --ignore-case
	     Perform case insensitive matching.  By default, grep is case sen-
	     sitive.
     -R, -r, --recursive
	     Recursively search subdirectories listed.
     -l, --files-with-matches
	     Only the names of files containing selected lines are written to
	     standard output.  grep will only search a file until a match has
	     been found, making searches potentially less expensive.  Path-
	     names are listed once per file searched.  If the standard input
	     is searched, the string ``(standard input)'' is written.
```