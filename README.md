# About

## 概要

- 人間とAIが対話しながらアイデアを練り上げることで、構造化されたマンガの企画とストーリーラインが出来上がり、絵を描くあるいは画像を生成する手前までの制作が安定的に行えるようになるものを作りました
- 既にマンガを描いている人の制作を助け、少ない負担で作家性を発揮する作品制作が行えるようになることが期待できます
- さらに、これからマンガを描きたい人の参入障壁を下げ、マンガ制作に親しむ人工を増やすことにより、市場の成長に貢献できます
- 実装を行う技術がないため、最低限動くプロトタイプで提出させていただきます

## 開発の背景にある課題

- 生成AIの登場により、これまでマンガ制作に取り組んだことが無い、あるいはマンガ制作に挫折したことがある人が、AIを活用してマンガ制作を行いたいという機運が高まっている
- LLMを用いてアイデア、設定、プロット、シナリオなどを生成することは多く行われている
- 画像生成AIを使って、マンガの作画を行う試みは多く行われている
- しかし、マンガを描く人が制作過程に取り入れられるツールはまだ登場していない
    - マンガを描く人が作ったツールがない
    - マンガを描く制作過程が言語化されていない

## 仮説

- マンガを描く人間が、そのドメイン知識を言語化し、AIと協業できるツールを発明し、公開することで、マンガを描く人間にももっとAI活用がめられるだろう

## 提出物

### 動画

### 使用した技術

- python
- OpenAI API

### 新規制

- マンガ製作者のドメイン知識を分解して、構造化し、再現性を持たせることを試みた

### 実用性

- AIと対話しながら制作を進めることで思考への負荷を軽減できる
- 約1時間で、マンガの企画とプロットができあがる
- コストを少なく企画を量産できる

### 今後の展開

- ネームを制作する工程を言語化して再現性を持たせる＋AIに取り組ませることができるか実験する
- 人間による修正を行わなくてもよいように、特定の文脈（作家性、外部の資料など）を反映したベクトルデータベースを接続して、完全自動化できるか実験する
- 他の領域のドメイン課題に転用できるか実験する

##########
# Demo on Google colab

https://colab.research.google.com/drive/1rTMW-44jO-ZzqYA-0V_POo3jbPi4JnEQ?usp=sharing

# マンガの基本的な設定
## マンガのテーマ
### マンガのキーワード

```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次へ進んでください

keywords='''
アンドロイドの女性、会社員、AIと人間の恋
'''
```

## マンガに込めたいメッセージ

```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次へ進んでください

message='''

'''
```
```
#AIによる提案

message_gpt3 = gpt3(f"""
以下のテキストを抽象的に解釈して、
簡潔な物語のメッセージ
を提案せよ
\nキーワード {keywords}
""")
print("### Assistantの提案:\n" + message_gpt3)
```
```
#AIによる提案の採用または修正
#AIの提案が気に入った場合は、コピペしてください
#気に気に入らない場合は、修正して入力してください

message='''

'''
```
## マンガの萌え要素
```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次へ進んでください

moe='''

'''
```
```
#AIによる提案

moe_gpt3 = gpt3(f"""
以下のテキストを抽象的に解釈して、
読者が嬉しくなる要素を
提案せよ
\nキーワード {keywords}
\nメッセージ　{message}
""")
print("### Assistantの提案:\n" + moe_gpt3)
```
```
#AIによる提案の採用または修正
#AIの提案が気に入った場合は、コピペしてください
#気に気に入らない場合は、修正して入力してください

moe='''

'''
```
```
#AIによる提案の採用または修正
#AIの提案が気に入った場合は、コピペしてください
#気に気に入らない場合は、修正して入力してください

moe='''

'''
```
## マンガのテーマ
```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次へ進んでください

theme='''

'''
```
```
#AIによる提案

theme_gpt3 = gpt3(f"""
以下のテキストを抽象的に解釈して、
マンガのテーマ
を提案せよ
\nキーワード {keywords}
\nメッセージ　{message}
\n萌え要素 {moe}
""")
print("### Assistantの提案:\n" + theme_gpt3)
```
```
#AIによる提案の採用または修正
#AIの提案が気に入った場合は、コピペしてください
#気に気に入らない場合は、修正して入力してください

theme='''

'''
```
## 主人公の設定
### 主人公の名前
```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次へ進んでください

mename='''

'''
```
```
#AIによるマンガの主人公の名前の提案

mename_gpt3 = gpt3(f"""
以下のテキストを抽象的に解釈して、
キャラクターの名前を
提案せよ
\nキーワード {keywords}
\nメッセージ　{message}
\nテーマ {theme}
""")
print("### Assistantの提案:\n" + mename_gpt3)
```
```
#AIによるマンガの主人公の名前の修正

mename='''
アイリス
'''
```
### 主人公の主義
#### 主人公が渇望していること
- 主人公の強い欲求や渇望していること、どうしても手に入れたいもの
```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次のコードブロックを実行してください

mewants='''

'''
```
```
#AIによる主人公の渇望していることの提案

mewants_gpt3 = gpt3(f"""
以下のテキストを抽象的に解釈して、
主人公の渇望していることを
提案せよ
\nキーワード {keywords}
\nメッセージ　{message}
\nテーマ {theme}
""")
print("### Assistantの提案:\n" + mewants_gpt3)
```
```
#AIによるマンガの主人公の名前の修正

mewants='''

'''
```
#### 主人公が絶対やりたくないこと

- 主人公が避けたいこと、どうしてもやりたく無いこと

```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次のコードブロックを実行してください

meavoid='''

'''
```
```
#AIによる提案

meavoid_gpt3 = gpt3(f"""
以下のテキストを抽象的に解釈して、
主人公が絶対やりたくないことを
提案せよ
\nキーワード {keywords}
\nメッセージ　{message}
\nテーマ {theme}
\n主人公が渇望していること　{mewants}
""")
print("### Assistant1の提案:\n" + meavoid_gpt3)
```
```
#AIによる主人公が絶対に避けたいことの修正

meavoid='''

'''
```
```
# 主人公の主義
meizm = "主人公が渇望していること：" + mewants + "\n主人公が絶対に避けたいこと：" + meavoid
print(meizm)
```
### 主人公の性質
#### 主人公が備えている特別な能力や強み
```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次へ進んでください

meabili='''

'''
```
```
#AIによる提案

meabili_gpt3 = gpt3(f"""
以下のテキストを抽象的に解釈して、
主人公が備えている特別な能力や強みを
提案せよ
\nキーワード {keywords}
\nメッセージ　{message}
\nテーマ {theme}
\n主人公の主義　{meizm}
""")
print("### Assistantの提案:\n" + meabili_gpt3)
```
```
#AIによる提案の採用または修正
#AIの提案が気に入った場合は、コピペしてください
#気に気に入らない場合は、修正して入力してください

meabili='''

'''
```
#### 主人公が物語の中で担っている役割
```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次へ進んでください

merole='''

'''
```
```
#AIによる提案

merole_gpt3 = gpt3(f"""
以下のテキストを抽象的に解釈して、
主人公が物語の中で担っている役割を
提案せよ
\nキーワード {keywords}
\nメッセージ　{message}
\nテーマ {theme}
\n主人公の主義　{meizm}
""")
print("### Assistantの提案:\n" + merole_gpt3)
```
```
#AIによるマンガの主人公が備えている特別な能力や強みの修正

merole='''

'''
```

```
#主人公の性質
meprsn = "主人公の能力:" + meabili + "\n主人公の役割:" + merole
print(meprsn)
```
## 主人公と対立関係にあるキャラクター
### 主人公と対立関係にあるキャラクターの関係性
- 主人公と対立する立場のキャラクターは敵でもいいし、パートナーでもいいし、恋人や家族でもいいし、人間以外の存在でも構いません
```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次のコードブロックを実行してください

theyrelation='''

'''
```

```
#AIによる提案

theyrelation_gpt3 = gpt3(f"""
以下のテキストを抽象的に解釈して、
主人公と対立関係にあるキャラクターとの関係を
提案せよ
\nテーマ {theme}
\n主人公の主義　{meizm}
\n主人公の性質　{meprsn}
""")
print("### Assistantの提案:\n" + theyrelation_gpt3)
```

```
#AIによる提案の採用または修正
#AIの提案が気に入った場合は、コピペしてください
#気に気に入らない場合は、修正して入力してください

theyrelation='''

'''
```
## 主人公と対立関係にあるキャラクターの主義
### 主人公と対立関係にあるキャラクターの渇望していること
```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次へ進んでください

theywants='''

'''
```

```
#AIによる提案

theywants_gpt3 = gpt3(f"""
以下のテキストを抽象的に解釈して、
主人公と対立関係にあるキャラクターの渇望していることを
提案せよ
\nテーマ {theme}
\n主人公の主義　{meizm}
\n主人公の性質　{meprsn}
\n主人公と対立関係にあるキャラクターとの関係　{theyrelation}
""")
print("### Assistantの提案:\n" + theywants_gpt3)
```

```
#AIによる提案の採用または修正
#AIの提案が気に入った場合は、コピペしてください
#気に気に入らない場合は、修正して入力してください

theywants='''

'''
```

### 主人公と対立関係にあるキャラクターの絶対にやりたくないこと
```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次へ進んでください

theyavoid='''

'''
```

```
#AIによる提案

theyavoid_gpt3 = gpt3(f"""
以下のテキストを抽象的に解釈して、
主人公と対立関係にあるキャラクターの絶対にやりたくないことを
提案せよ
\nテーマ {theme}
\n主人公の主義　{meizm}
\n主人公の性質　{meprsn}
\n主人公と対立関係にあるキャラクターとの関係　{theyrelation}
""")
print("### Assistantの提案:\n" + theyavoid_gpt3)
```

```
#AIによる提案の採用または修正
#AIの提案が気に入った場合は、コピペしてください
#気に気に入らない場合は、修正して入力してください

theyavoid='''
主人公の精神が安定し、理不尽な仕事を避ける判断ができること
'''
```

```
#主人公と対立関係にあるキャラクターの主義
theyizm = "主人公と対立関係にあるキャラクターの渇望:" + theywants + "\n主人公と対立関係にあるキャラクターの避けたいこと:" + theyavoid
#theyizm
```

## 主人公と対立関係にあるキャラクターの性質
### 主人公と対立関係にあるキャラクターの能力
```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次のコードブロックを実行してください

theyabili ='''

'''
```

```
#AIによる提案

theyabili_gpt3 = gpt3(f"""
以下のテキストを抽象的に解釈して、
主人公と対立関係にあるキャラクターの特別な能力を
提案せよ
\nテーマ {theme}
\n主人公の主義　{meizm}
\n主人公の性質　{meprsn}
\n主人公と対立関係にあるキャラクターとの関係　{theyrelation}
""")
print("### Assistantの提案:\n" + theyabili_gpt3)
```

```
#AIによる提案の採用または修正

theyabili='''

'''
```

### 主人公と対立関係にあるキャラクターの役割
```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次へ進んでください

theyrole = '''

'''
```

```
#AIによる提案

theyrole_gpt3 = gpt3(f"""
以下のテキストを抽象的に解釈して、
主人公と対立関係にあるキャラクターの担っている役割を
提案せよ
\nテーマ {theme}
\n主人公の主義　{meizm}
\n主人公の性質　{meprsn}
\n主人公と対立関係にあるキャラクターとの関係　{theyrelation}
""")
print("### Assistantの提案:\n" + theyrole_gpt3)
```

```
#AIによる提案の採用または修正
#AIの提案が気に入った場合は、コピペしてください
#気に気に入らない場合は、修正して入力してください

theyrole = '''

'''
```

```
#主人公と対立関係にあるキャラクターの性質

theyprsn = "主人公と対立関係にあるキャラクターの能力" + theyabili + "\n主人公と対立関係にあるキャラクターの役割" + theyrole
print(theyprsn)
```

## 主人公と対立関係にあるキャラクターの名前
```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次へ進んでください

theyname ='''

'''
```

```
#AIによる提案

theyname_gpt3 = gpt3(f"""
以下のテキストを抽象的に解釈して、
主人公と対立関係にあるキャラクターの名前を
提案せよ
\nテーマ {theme}
\n主人公の名前　{mename}
\n主人公と対立関係にあるキャラクターとの関係　{theyrelation}
\n主人公と対立関係にあるキャラクターの主義　{theyizm}
\n主人公と対立関係にあるキャラクターの性質　{theyprsn}
""")
print("### Assistantの提案:\n" + theyname_gpt3)
```

```
#AIによる提案の採用または修正

theyname='''

'''
```

## 主人公を導く者
### 主人公を導く者との関係性
- 主人公を導く者は、師匠でもいいし、親や上司、パートナーでもいいし、恋人でもいいし、人間以外の存在でも構いません
```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次のコードブロックを実行してください

ldrrelation = '''

'''
```

```
#AIによる提案

ldrrelation_gpt3 = gpt3(f"""
以下のテキストを抽象的に解釈して、
主人公と主人公を導く者との関係性を
提案せよ
\nキーワード {keywords}
\nテーマ {theme}
\n主人公の主義　{meizm}
\n主人公の性質　{meprsn}
""")
print("### Assistantの提案:\n" + ldrrelation_gpt3)
```

```
#AIによる提案の採用または修正
#AIの提案が気に入った場合は、コピペしてください
#気に気に入らない場合は、修正して入力してください

ldrrelation = '''

'''
```

```
#AIによる提案の採用または修正
#AIの提案が気に入った場合は、コピペしてください
#気に気に入らない場合は、修正して入力してください

ldrrelation = '''

'''
```

### 主人公を導く者の主義
#### 主人公を導く者が渇望していること
```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次へ進んでください

ldrwants = '''

'''
```

```
#AIによる提案

ldrwants_gpt3 = gpt3(f"""
以下のテキストを抽象的に解釈して、
主人公を導く者が渇望していることを
提案せよ
\nテーマ {theme}
\n主人公の主義　{meizm}
\n主人公の性質　{meprsn}
\n主人公を導く者との関係性　{ldrrelation}
""")
print("### Assistantの提案:\n" + ldrwants_gpt3)
```

```
#AIによる提案の採用または修正
#AIの提案が気に入った場合は、コピペしてください
#気に気に入らない場合は、修正して入力してください

ldrwants = '''

'''
```

#### 主人公を導く者が絶対にやりたくないこと
```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次へ進んでください

ldravoid = '''

'''
```

```
#AIによる提案

ldravoid_gpt3 = gpt3(f"""
以下のテキストを抽象的に解釈して、
主人公を導く者が絶対にやりたくないことを
提案せよ
\nテーマ {theme}
\n主人公の主義　{meizm}
\n主人公の性質　{meprsn}
\n主人公を導く者との関係性　{ldrrelation}
""")
print("### Assistantの提案:\n" + ldravoid_gpt3)
```

```
#AIによる提案の採用または修正
#AIの提案が気に入った場合は、コピペしてください
#気に気に入らない場合は、修正して入力してください

ldravoid = '''

'''
```

### 主人公を導く者の性質
#### 主人公を導くものが備えている特別な能力
```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次へ進んでください

ldrabili = '''

'''
```

```
#AIによる提案

ldrabili_gpt3 = gpt3(f"""
以下のテキストを抽象的に解釈して、
主人公を導くものが備えている特別な能力を
提案せよ
\nテーマ {theme}
\n主人公を導く者の主義 {ldrizm}
\n主人公を導く者との関係性　{ldrrelation}
""")
print("### Assistantの提案:\n" + ldrabili_gpt3)
```

```
#AIによる提案の採用または修正
#AIの提案が気に入った場合は、コピペしてください
#気に気に入らない場合は、修正して入力してください

ldrabili = '''
主人公をたぶらかし、怠惰な惰性に溺れさせること
'''
```
#### 主人公を導く者が作中で担っている役割
```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次へ進んでください

ldrrole = '''

'''
```

```
#AIによる提案

ldrrole_gpt3 = gpt3(f"""
以下のテキストを抽象的に解釈して、
主人公を導く者が作中で担っている役割
を提案せよ
\nテーマ {theme}
\n主人公を導く者の主義 {ldrizm}
\n主人公を導く者との関係性　{ldrrelation}
""")
print("### Assistantの提案:\n" + ldrrole_gpt3)
```

```
#AIによる提案の採用または修正
#AIの提案が気に入った場合は、コピペしてください
#気に気に入らない場合は、修正して入力してください

ldrrole = '''

'''
```

```
#主人公を導く者の性質

ldrprsn = "主人公を導くものが備えている能力" + ldrabili + "\n主人公を導く者が作中で担っている役割" + ldrrole
print(ldrprsn)
```

## 主人公を導く者の名前
```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次のコードブロックを実行してください

ldrname ='''

'''
```

```
#AIによる提案

ldrname_gpt3 = gpt3(f"""
以下のテキストを抽象的に解釈して、
主人公を導く者の名前
を提案せよ
\nテーマ {theme}
\n主人公を導く者の主義 {ldrizm}
\n主人公を導く者の性質 {ldrprsn}
""")
print("### Assistantの提案:\n" + ldrname_gpt3)
```

```
#AIによる提案の採用または修正
#AIの提案が気に入った場合は、コピペしてください
#気に気に入らない場合は、修正して入力してください

ldrname = '''

'''
```
## マンガのアイコン性
- アイコン性とは、マンガの第一印象を決定づける要素です
### 物語の世界観
- 物語の世界観を表すキーワードまたは文章
```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次へ進んでください

plsp = '''

'''
```

```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次へ進んでください

genre = '''

'''
```

```
#AIによる提案

genre_gpt3 = gpt3(f"""
以下のテキストを抽象的に解釈して、
マンガのジャンル
を提案せよ
\nテーマ {theme}
\n主人公の主義　{meizm}
\n主人公の性質　{meprsn}
""")
print("### Assistantの提案:\n" + genre_gpt3)
```

```
#AIによる提案の採用または修正
#AIの提案が気に入った場合は、コピペしてください
#気に気に入らない場合は、修正して入力してください

genre = '''

'''
```

### マンガのキービジュアル
- マンガの印象を一目で決定づけるようなキービジュアルを言葉で描写してください
```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次へ進んでください

keyvisu = '''

'''
```

```
#AIによる提案

keyvisu_gpt3 = gpt3(f"""
以下のテキストを抽象的に解釈して、
マンガの印象を一目で決定づけるようなキービジュアルを、視覚から情報を得ることが難しい人のために説明してください
\nテーマ {theme}
\n主人公の主義　{meizm}
\n主人公の性質　{meprsn}
\n物語のジャンル {genre}
""")
print("### Assistantの提案:\n" + keyvisu_gpt3)
```

```
#AIによる提案の採用または修正
#AIの提案が気に入った場合は、コピペしてください
#気に気に入らない場合は、修正して入力してください

keyvisu = '''

'''
```

## マンガのアイコン性まとめ
```
#AIによる提案

plsp = gpt3(f"""
以下のテキストを要約して、
物語の世界観を
提案せよ
\n物語のジャンル {genre}
\nマンガのキービジュアル {keyvisu}
""")

icon_gpt3 = gpt3(f"""
以下のテキストを要約して、
マンガの魅力を
提案せよ
\n物語の世界観 {plsp}
\nマンガのキービジュアル {keyvisu}
""")
print("### Assistantの提案:\n" + icon_gpt3)
```

```
#AIによる提案の採用または修正
#AIの提案が気に入った場合は、コピペしてください
#気に気に入らない場合は、修正して入力してください

icon = '''

'''
```
## マンガのアイデア性
- アイデア性とは、このマンガ面白そう！を思わせる要素です
### 主人公にとって望ましい状況
```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次へ進んでください

situposi = '''

'''
```

```
#AIによる提案

situposi_gpt3 = gpt3(f"""
以下のテキストを抽象的に解釈して、
主人公にとって望ましい状況を
提案せよ
\nテーマ {theme}
\nマンガの魅力 {icon}
\n主人公が渇望していること　{mewants}
""")
print("### Assistantの提案:\n" + situposi_gpt3)
```

```
#AIによる提案の採用または修正
#AIの提案が気に入った場合は、コピペしてください
#気に気に入らない場合は、修正して入力してください

situposi = '''

'''
```
### 主人公にとって望ましくない状況
```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次へ進んでください

situnega = '''

'''
```

```
#AIによる提案

situnega_gpt3 = gpt3(f"""
以下のテキストを抽象的に解釈して、
主人公にとって望ましくない状況を
提案せよ
\nテーマ {theme}
\nマンガの魅力 {icon}
\n主人公が絶対に避けたいこと　{meavoid}
""")
print("### Assistantの提案:\n" + situnega_gpt3)
```

```
#AIによる提案の採用または修正
#AIの提案が気に入った場合は、コピペしてください
#気に気に入らない場合は、修正して入力してください

situnega = '''
絶えず仕事に疲れ、ストレスを感じることで精神的な安定を求める生き方
'''
```

### マンガのアイデア性-まとめ
```
#AIによる提案

idea_gpt3 = gpt3(f"""
以下のテキストを要約して、
マンガの面白みを
提案せよ
\n主人公の主義 {meizm}
\n主人公の性質 {meprsn}
\n主人公にとって望ましい状況 {situposi}
\n主人公にとって望ましくない状況 {situnega}
""")
print("### Assistantの提案:\n" + idea_gpt3)
```

```
#AIによる提案の採用または修正
#AIの提案が気に入った場合は、コピペしてください
#気に気に入らない場合は、修正して入力してください

idea = '''

'''
```
## マンガのログライン
- ログラインは、どんな世界で、どんな主人公が、どんな状況の中で、何をしようとする話かを簡潔に説明するものです
```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次へ進んでください

logline = '''

'''
```

```
#AIによる提案

logline_gpt = gpt4(f"""
以下のテキストを抽象的に解釈して、
どんな世界で、どんな主人公が、どんな状況の中で、何をしようとする話かを
端的に表現せよ
\nマンガの魅力 {icon}
\n主人公の主義　{meizm}
\n主人公の性質　{meprsn}
\nマンガのアイデア性 {idea}
""")
print("### Assistant1の提案:\n" + logline_gpt)
```

```
#AIによる提案の採用または修正
#AIの提案が気に入った場合は、コピペしてください
#気に気に入らない場合は、修正して入力してください

logline = '''

'''
```

## マンガのタイトル
```
#決まっている場合は、入力してください
#決まっていない場合は、このコードブロックはスキップして、次へ進んでください

title='''

'''
```

```
#AIによる提案

title_gpt = gpt4(f"""
以下のテキストを抽象的に解釈して、
マンガのタイトルを
3つ提案せよ
\nマンガのテーマ {theme}
\nマンガのログライン {logline}
""")
print("### Assistantの提案:\n" + title_gpt)
```

```
#AIによる提案の採用または修正
#AIの提案が気に入った場合は、コピペしてください
#気に気に入らない場合は、修正して入力してください

title = '''

'''
```
