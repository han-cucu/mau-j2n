# Git
#### Gitとは
ファイルのバージョン管理をするツール。ソースコードを管理することが多いが、コンピュータ上のあらゆる種類のファイルを管理することができる。バージョン管理機能として、ファイルの変更履歴を保存したり、ブランチ機能で変更履歴を枝のように分岐して保存したり、マージ機能で分岐した変更履歴を統合したりできる。  
分散型バージョン管理というシステムになっている。リポジトリ(バージョン管理の対象になるファイル、ディレクトリ、変更履歴などのデータのまとまり)を、複数のコンピュータに分散しミラーリングして管理することができる。  

#### 便利な点
- バージョン管理機能による便利な点
    - 過去のファイルの状態や変更履歴を確認できる。
    - ファイルやプロジェクト丸ごとを過去の状態に戻したり、再び最新の変更の状態に戻したりできる。
    - 問題が起こっているかもしれない変更は誰がいつ加えたか確認することができる。
- 分散管理による便利な点
    - データの修復が可能。管理の中心となるコンピュータが故障したとしても、別のコンピュータで同リポジトリを管理していれば、データを復活することができる。
    - 複数人で変更をする場合、各々のコンピュータ上のリポジトリを変更した後に、複数の変更履歴を統合していくことができるため、同時に変更作業をすることが簡単である。

<br>

# GitHub
#### GitHubとは
Gitの仕組みを利用してリポジトリを管理するWebサービス。分散型バージョン管理の機能を活かして、リポジトリをサーバで管理でき、他の開発者と共有したり、Web上で公開することができる。  
リポジトリを管理した上で、GUIによるGitの操作ができる。  
また、複数人の共同開発、オープンソース開発に役立つようなコミュニケーションをサポートする機能がある。  

#### 便利な点
- リポジトリをホスティングするサーバを管理、保守する手間を省くことができるため、分散型バージョン管理の恩恵を手軽に受けることができる。
- リポジトリに関する情報をグラフィカルに確認、操作することができる。ファイルの中身、コミット履歴、ブランチなどをブラウザから確認することができるため、わかりやすい。
- プルリクエスト機能を利用すれば、ブランチのマージを、開発者間でテキストコミュニケーションを取りながら進めることができる。s
- イシュー機能を利用すれば、プロジェクトやソースコードの課題を管理でき、掲示板のようにコミュニケーションを取ることができる。

<br>

# Markdown
#### Markdownとは
Markdownは、HTMLやXMLなど文書を記述するためのマークアップ言語を、読み書きしやすく簡潔化した軽量マークアップ言語のひとつである。  
Markdown記法で文章を書く際は、特定の記号を使うことで段落や見出しや装飾、リンクなどの構造を定義することができる。また、Markdownで記述することで定義した構造は、コンバータを通すことでHTMLやXMLのマークアップ言語、pptxやpdfなどに変換することができる。  

#### 便利な点
- 文章構造を明示できる。
- 記法のルールが簡単で覚えやすく、扱いやすい。
- いろいろなフォーマットに変換することができるので、ドキュメント作成が効率的になる。

<br>

# README.md公開作業メモ
#### 手順を整理
リポジトリの作成方法を検索し、以下のドキュメントを参考に、リポジトリを作成することにした。  
[GitHub Docs - はじめに / リポジトリを作成する](https://docs.github.com/ja/get-started/quickstart/create-a-repo#create-a-repository)  

ドキュメントではgithub上でREADME.mdの編集・コミットをしているが、今回は課題の条件のためにCUIのGit操作でローカルリポジトリから変更、プッシュする。  

以下の手順でREADME.mdをgithub上で公開しようと試みる。
1. githubにログイン
2. githubのGUIでリモートリポジトリを作成
    * リポジトリ名は**mau-j2n**
3. リモートリポジトリをローカルにクローン
4. 予め作成していたREADME.mdをリポジトリ配下におく
5. CUIのgit操作により変更をリモートリポジトリへ反映する
    - git add README.md
    - git commit -m "git init"
    - git push
6. GitHub上で、README.mdが閲覧できることを確認する。
7. 閲覧できたら、修正が必要な箇所を探し修正する。(5.と同様の反映方法)
<br>

#### 1.GitHubにログイン
GitHubにログインする。
SettingsからSSHKeyが登録されていることを確認。
<br>

#### 2.GitHubのGUIでリモートリポジトリの作成

1. GitHubページの右上の +ボタン>New Repositoryをクリック 
2. リポジトリの情報を入力する
    * リポジトリ名を入力 (mau-j2n)
    * 今回READMEは作成済みのため、[Initialize this repository with a README]のチェックは外しておいた
3. [Create Repository]をクリックし、リポジトリが作成された
<br>

#### 3.リモートリポジトリをローカルにクローン
1. mau-j2nディレクトリを作成した
2. クローンを実行
    - `git clone git@github.com:han-cucu/mau-j2n.git`
3. worningが発生した。
    ![clone_worning](/clone_worning.png)  
    > Cloning into 'mau-j2n'...
    warning: You appear to have cloned an empty repository
    - *空のリポジトリをクローンすることはできないようだった* (追記: このタイミングのクローン後にgit statusを実行してみたがgitコマンドが使えなかったため、クローンに失敗していると勘違いした。クローンされる階層を勘違いしており、実際は装丁よりひとつ下の階層にクローンがされていた。)
<br>

#### 改めて手順を整理

Githubで案内されている方法に則り、
ローカルリポジトリを作成してから、リモートリポジトリに登録することにする。  
以下の案内を参考にした。  
![create_a_new_repository](/create_a_new_repository.png)  


手順を以下に変更した。
1. githubにログイン
2. githubのGUIでリモートリポジトリを作成
    * リポジトリ名は**mau-j2n**
3. ~~リモートリポジトリをローカルにクローン~~
4. ~~予め作成していたREADME.mdをリポジトリ配下におく~~
5. ローカルリポジトリを作成、READMEをコミット
    - cd mau-j2n
    - git init
    - git add README.md
    - git commit -m "add README"
    - git remote add origin git@github.com:han-cucu/mau-j2n.git
    - git push
6. CUIのgit操作により変更をリモートリポジトリへ反映する
    - git add README.md
    - git commit -m "git init"
    - git push
7. GitHub上で、README.mdが閲覧できることを確認する。
8. 閲覧できたら、修正が必要な箇所を探し修正する。(5.と同様の反映方法)
<br>

#### 5.ローカルリポジトリを作成、READMEをコミット

*作業を開始しようとしたところ、**3.リモートリポジトリをローカルにクローン**で行ったクローンに成功していることに気づいた、、クローン後にgit statusが使えなかったのでクローンに失敗していると勘違いしてしまった。ひとつ下の階層にクローンされていた*  
  
もともと予定していた以下の手順で作成することにする。  

>1. githubにログイン
>2. githubのGUIでリモートリポジトリを作成
>    * リポジトリ名は**mau-j2n**
>3. リモートリポジトリをローカルにクローン
>4. 予め作成していたREADME.mdをリポジトリ配下におく
>5. CUIのgit操作により変更をリモートリポジトリへ反映する **(追記)** 
>    - git add README.md
>    - git commit -m "git init"
>    - git push
>6. GitHub上で、README.mdが閲覧できることを確認する。
>7. 閲覧できたら、修正が必要な箇所を探し修正する。(5.と同様の反映方法)
<br>

#### 4. 予め作成していたREADME.mdをリポジトリ配下におく
- mau-j2n/README.mdとなるように配置した
- `git status`で変更差分となっていることを確認
<br>

#### 5. CUIのgit操作により変更をリモートリポジトリへ反映する
- `git add README.md`
- `git commit -m "add README"`
- `git push`
<br>

#### 6. GitHub上で、README.mdが閲覧できることを確認する
- https://github.com/han-cucu/mau-j2n にアクセスし、READMEが読めることを確認した
<br>

#### 7. 閲覧できたら、修正が必要な箇所を探し修正する。(5.と同様の反映方法)
- 修正1. VSCodeで編集していたREADMEのパスとリポジトリにコミットしたREADMEのパスがずれていたため、READMEの内容が古くなっていた。最新のファイルを置き換えて修正。VSCodeで編集中のパスにファイルが存在しない場合、保存するとファイルが生成されてしまうようだった。

- 修正2. 改行をいれた。VSCodeのプラグインであるMarkDown Preview Enhancedでは改行コード無しで改行してくれるようで、Github上で見たときに改行がされていないことに気づいた。
- 修正3. 画像を追加した。
- 修正4. 文言を修正した。
- 修正5. 見出しサイズを修正した。
- 修正6. 詰まったところの理由を追記。








