## voicevox等の正確な発音取得


# Datasets

* CMU 辞書
  
  カスタム辞書にすることも可。

  [このサイト](http://www.speech.cs.cmu.edu/cgi-bin/cmudict)から、発音記号のデータセットを取得

  発音記号をひらがな読みに変換し、json形式で
```json
{
  "a": "あ",
  "python": "ぱいそん",
  ...
}
```
  のように`cmu.json`で保存してください.

* BigAlphabet

  大文字アルファベットのそのまま読みを対応させるための辞書
```json
{
  "a": "えい",
  "b": "びい",
  "c": "しい",
  ...
}
```
  上記を`bigalphabet.json`で保存

## create `.db` file

sqlite3のファイル形式に。

```sh
$ python createDB.py
```

`datasets.db` が作成されます

# Install, Build, Run

## Local
```sh
$ pip install -r requirements.txt
# or
$ pip install jaconv mecab-python3 fastapi uvicorn[standard]
```

```sh
$ python main.py
```

## Docker

```sh
$ docker build . -t hastuon
```
```sh
$ docker run -p 10487:10487 hastuon
```