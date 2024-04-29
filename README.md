## 概要

- AIと対話しながらアイデアを練り上げることで、マンガの企画が出来上がり、マンガ制作が安定的に行えるようになるものを作りました
- 既にマンガを描いている人の制作を助け、少ない負担で作家性を発揮する作品制作が行えるようになることが期待できます
- さらに、これからマンガを描きたい人の参入障壁を下げ、マンガ制作に親しむ人口を増やすことにより、市場の成長に貢献できます

## 開発の背景にある課題

- 生成AIを使って、アイデア、設定、プロット、シナリオなどを生成する試みは多く行われている
- マンガを描く人のドメイン知識が言語化されておらず、制作過程の再現性が担保されていない
- 作家自身の思考や作業量の負担が大きく、作家活動を行うことの負荷が高い

## 仮説

- マンガを描く人間が、そのドメイン知識を言語化し、AIと協業できるツールを発明し、公開することで、マンガを描く人の負荷を減らし、マンガへの参入障壁も下げられるだろう

### 構造の言語化

- v1　https://github.com/masa-jp-art/Manga-planning-assistant/blob/main/manga-structure-v1.md
- v2　https://github.com/masa-jp-art/Manga-planning-assistant/blob/main/manga-structure-v2.md

### 概念図

- https://miro.com/app/board/uXjVMdFD3xo=/?share_link_id=953476929380
- v1 ![Manga-Planning-AI](https://github.com/masa-jp-art/Manga-planning-assistant/assets/120908357/54962eea-bc4e-41bc-aafe-b20da9135c3d)
- v2 ![Manga-Planning-AI-v2](https://github.com/masa-jp-art/Manga-planning-assistant/assets/120908357/566b9bbc-63f5-491f-9867-9fb1e28f6bf7)

## 使用した技術

- python
- OpenAI API
- Claude API

## 新規制

- マンガ製作者のドメイン知識を分解して、構造化し、再現性を持たせることを試みた

## 実用性

- AIと対話しながら制作を進めることで思考への負荷を軽減できる
- AIの提案を修正することで、操作する人間の作家性を反映できる
- 短時間でマンガの企画を作れる

## 今後の展開

- ネームを制作する工程を言語化してAIで再現性を持たせることができるか実験する
- 特定の文脈（作家性、外部の資料など）を反映したベクトルデータベースを接続して、完全自動化できるか実験する
- 他の領域のドメイン課題に転用できるか実験する

# Demo on Google colab
- 20240421--manga-planning-AI-v2
  - https://colab.research.google.com/drive/1N1hCMaIDOwqMSkyXsWnjvOeybMB8jHvZ#scrollTo=Frxf4W3CMLOY
- 20240308-manga-planning-AI-v1
  - https://colab.research.google.com/drive/1rTMW-44jO-ZzqYA-0V_POo3jbPi4JnEQ?usp=sharing

## examples
- v1
  - https://drive.google.com/open?id=1VDXoXdNxDfB4UrD1BylKoTmOzgIeghhirOd3BfOQJcs
  - https://drive.google.com/open?id=1dpHWuiY4S62u4_Gj5iYAF5BJtgYxlNebhzKfqvBslU4
  - https://drive.google.com/open?id=1e1ifeS2CBZLbX6eGkcBEQiQTaZT5eET77Bwed_4o36s
- v2
  - https://drive.google.com/open?id=1ezIAuWARM3gU4IVNq-zhi8QaAA-yuPXIb4AlBHjiE9U
  - https://drive.google.com/open?id=1qvlKPa_vNgXDGrKbIaR1GENgMdvSoRQZ4LL5T6R0JgM
  - https://drive.google.com/open?id=1VZaazcqKA28O3kTEEGt4ktGyJee5kdOPLgac730cIfw

# 関連
- 生成AIなんでも展示会
  - note　https://note.com/msfmnkns/n/n89d7a4caefba?magazine_key=m86cfe3c710d4
  - YouTube　https://youtu.be/0SyZyDP-Mmc
- 東京AI祭-技術大合戦
  - ハッカソンページ　https://app.akindo.io/communities/K84OqRGBqC7PLjg0/products/aA40gjnxMu8nq2xRN
  - note　https://note.com/msfmnkns/n/nfd3bb8855216?magazine_key=m86cfe3c710d4
  - YouTube　https://www.youtube.com/watch?v=B5-PF-ifRJw
