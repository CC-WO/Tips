# Python 仮想環境の構築

## 目指すところ

Pythonを任意のバージョンと任意のパッケージを使えるようにし、Visual Studio Code上でデバッグできるようにする.

## 環境

Mac OS Catalina Version 10.15.7

Python 3.7 later

## 仮想環境全貌

Pythonの仮想環境を構築する上でのポイントは2つある.

- Pythonのバージョンを管理すること.
- Pythonのライブラリ（パッケージ）を管理すること.

多くの場合は、任意のPythonのバージョンの上に、自由なライブラリを入れてPythonを実行したいはずだ.

そこで今回は, バージョンの管理にpyenv, ライブラリの管理にvenvを用いる.

venvはPython3.7以降では標準機能のため, 通常そのまま使える. pyenvは別途使えるようにする必要がある.

## 前準備

pyenvを使えるようにする. 手順は基本的に以下のpyenvのGitHubのREADMEを参考にしていただきたい.

[https://github.com/pyenv/pyenv#installation](https://github.com/pyenv/pyenv#installation)

気をつけていただきたいのは, Macの標準ターミナルはCatalina以降zsh系になっていること.

そのため, pyenvの環境変数はzshとbashに対して通しておくとよいだろう.

## 仮想環境の構築

venvとpyenvが使えるようになったら, 実際にPythonの環境を構築していく,

今回例として, Python 3.6.4でnumpyを使えるようになるところを目指す. 一連の手順はpyenvでPATHを通したターミナルで行うこと.

```terminal
# pyenvで利用可能なPythonバージョン一覧を確認
$ pyenv install --list

# Python3.6.4をインストール
$ pyenv install 3.6.4

# インストールされているPython一覧を確認する
$ pyenv versions
* system (set by /Users/user/.pyenv/version)
  3.6.4

# バージョン3.6.4に切り替える
$ pyenv shell 3.6.4

# pyenvよってPATHに挿入されたPythonインタプリタを見にいっている
which python
/Users/User/.pyenv/shims/python

# 仮想環境に入る
$ source .venv/bin/activate

# venvで新しい仮想環境を構築
$ python3 -m venv .venv

# 仮想環境内のPythonのバージョン確認(仮想環境内に入ればPythonのエイリアスがPython 3.6.4を指す)
(.venv)$ python -V
Python 3.6.4

# numpyのインストール 仮想環境venvにパッケージが追加される
$ pip install --upgrade pip
$ pip install numpy

# 仮想環境のPythonは.venv/内のpythonを見にいっている
(.evn)$ which python
./.venv/bin/python
```

## Visual Studio Code上でのデバッグ

まずは上記の手順をWorkspace or Directoryを開いたVSCode上のターミナルで実行する.

次にVisual Studio Codeで構築した仮想環境上でデバッグを行うための手順は2つ.

- Python インタプリタをpyenvで作成したバージョンに切り替える

  上記までできていれば, コマンドパレッット(Cmd+Shift+P)で`Python: Select Interpreter`を実行すると, `Python 3.6.4 64-bit ('.venv')` を選択できるようになっている.

- Python デバッグ用のlaunch.jsonを作成する

  Run(左バーの△+虫マーク)から`create a launch.json file`を選択し, `Python`→`Python file`と選択していけば, launch.jsonが作成され. デバッグ用のPATHが通る.

これで今回構築した仮想環境の上でVSCodeのデバッグ機能を使うことができる.

## 仮想環境構築後のケア

pyenvの切り替え

```terminal
# バージョン3.6.4に切り替える
$ pyenv shell 3.6.4

＃ 現在のバージョンを確認する
$ pyenv version
3.6.4 (set by PYENV_VERSION environment variable)

# バージョン3.8.3から元にもどす
$ pyenv shell system
```

venvの切り替え

```terminal
# 仮想環境に入る
$ source .venv/bin/activate

# 仮想環境から出る
$ deactivate
```

Gitでの管理

.venvフォルダはgitignoreでトレースの対象から外した方がよいだろう

## 参考文献

- [https://messefor.hatenablog.com/entry/2020/08/22/181519](https://messefor.hatenablog.com/entry/2020/08/22/181519)
