# プロジェクトに貢献する

[SoftwareCarpentry][swc-site]と[DataCarpentry][dc-site]はオープンソースのプロジェクトです。
コミュニティーからの資料提供・ご協力、例えば、
新しいレッスン、
既存の資料の修正、
バグレポート、
変更点のレビューなど、どんなに些細な変更も歓迎いたします。

## 貢献する方法

このプロジェクトに貢献することにより、
自身が提供したコンテンツを[私達のライセンス](License.md)に基づき配布する事に同意するものとします。
ご協力と引き換えに、
私達はあなたが提供する変更点・問題点などを検討し、
できるだけ早くコミュニティーの一員になれるよう尽力いたします。
[Software Carpentry][swc-site]と[Data Carpentry][dc-site]の一員になられた際には、
私達の[行動規範](https://docs.carpentries.org/topic_folders/policies/code-of-conduct.html)を遵守する事に同意していただきます。

## 貢献する方法

一番簡単に貢献する方法は、
誤字、言葉遣い、
間違った内容などを
issue(イシュー)で報告する事です。
Issueを報告することによって、自分をコミュニティーに紹介し、
また、コミュニティーのメンバーと出会う良い機会にもなります。

1. [GitHub][github]アカウントをお持ちでない場合、
    [メール][contact]にてご連絡して下さい。
    ですが、
    以下の方法であればメールよりも早急に対応できる場合がありますので、そちらをお勧め致します。

2. [GitHub][github]アカウントをすでにお持ちである方・
    またはアカウントを[新たに作る][github-join]気がある方で、
    あまりGitに詳しくない・使い慣れていない方は、
    質問・提案などを[新しいイシュー][new-issue]として開いて下さい。
    イシューを開くことによって、コミュニティーから誰かをそのイシューに割り当て、
    スレッド化したディスカッションとして質問・提案に応答させていただくことができます。

3. Gitを使い慣れている方で、
    既存の資料を変更、または追加したい方は、
    プルリクエスト(Pull Request)にて変更点を提出して下さい。
    プルリクエストを使った提出方法は、[下記に記載されています](#using-github)。

## どこへ貢献するか

1.  このレッスンの内容を変更したい場合は、
    <https://github.com/swcarpentry/r-novice-gapminder>から編集して下さい。
    ウェブサイトはこちらから観覧いただけます：<https://swcarpentry.github.io/r-novice-gapminder>

2.  模範レッスンの内容を変更したい場合は、
    <https://github.com/carpentries/lesson-example>から編集して下さい。
    このリポジトリは模範レッスンの内容を記載しており、
    こちらから観覧できます：<https://carpentries.github.io/lesson-example>.

3.  ワークショップのウェブサイトに使われるテンプレートの内容を変更したい場合は、
    <https://github.com/carpentries/workshop-template>から編集して下さい。
    このリポジトリのホームページに、ワークショップに使うウェブサイトの設立方法が記載されており、
    <https://carpentries.github.io/workshop-template>から
    サイトの詳細なデザイン方針が観覧できます。

4.  `_includes`、または`_layouts`に保存されている、レッスンやワークショップのためのCSSファイル、ツール、
    HTML boilerplateなどを編集したい場合は、
    <https://github.com/carpentries/styles>から編集して下さい。

## 貢献していただきたい個所

新しい例を書く、すでにある例の改善、
ドキュメントのアップデート、
不明瞭な点、欠点、「動作に不具合がある」といった
[バグの報告][new-issue]など、
様々な方法で貢献していただくことができます。
どういったイシューを開いたら良いかわからない場合は、
[このリポジトリのイシュー][issues]、
[Data Carpentryのイシュー][dc-issues]、
もしくは[Software Carpentryのイシュー][swc-issues]を見てみて下さい。

すでにあるイシューへのコメントや、プルリクエストのレビューなども歓迎いたします。
皆さんで協力したほうが、良い結果につながります。
また、新しく加入された方の意見やレビューなどは特に重要視しています。
レッスンの資料を幾度となく見てきた方は特に見落としがちなのですが、
私達が提供している資料・コンテンツは、初めて資料を見る方などには、理解するのに時間が掛かる場合があるので、
通常とは違う視点からの意見は大変貴重なのです。

## 貢献していただきたくない個所

現在、通常のワークショップの時間内ではカバーしきれないほどの内容量がレッスンの資料に含まれています。
ですので、新たにレッスンに含められる項目やツールなどは求めておりません。
どうしても新しい内容を入れたい場合は、
(a)新しい内容を教えるために掛かるおおよその時間、
(b)新しい内容を入れる代わりにどの内容を取り出すか、
そして、取り出す理由をご説明下さい。
最初の点は、貢献する方々に可能かどうかを見極めていただくためです。
二つ目の点は、どちらの内容を有線するべきかを考えていただくためです。

上記に加え、一つのプラットホーム・OSでしか使用ができないなどといったプログラムのレッスン内容・資料などは求めておりません。
私達が提供するワークショップでは、Windows、Mac OS X、Linuxなど、違ったOSを使用するユーザーが来ることがあります。
そのため、新しいレッスンを作る際には、
先述の三つのOSに対応可能である必要があります。

## GitHubの使い方

GitHubから資料を提供したい場合は、
[GitHubでオープンソース・プロジェクトに貢献する方法][how-contribute]
を参照して下さい。
簡潔にまとめると：

1.  現在公開されているレッスン内容はリポジトリの`gh-pages`というブランチに保存されています
    (これはGitHubが自動的に変更点を公開させるためです)。
    そのため、全てのブランチは`gh-pages`から分岐させ、
    オリジナルの[リポジトリ][repo]の`gh-pages`を自身が分岐した`gh-pages`のブランチにマージ・合流させてから、
    内容を変更してください。
    他の内容・個所へ貢献することが難しくなるため、
    *オリジナルの`gh-pages`から直接内容を変更することはお控え下さい。*

2.  私達は[GitHub flow][github-flow]を使って変更点などを管理しています：
    1.  自身が持っているオリジナルのリポジトリのコピー(フォーク)に新しいブランチを作り、そのブランチで内容を変更します。
    2.  作ったブランチ内で変更点をコミットします。
    3.  そのブランチをGitHubのフォークにプッシュします。
    4.  自身のフォークからオリジナルの[リポジトリ][repo]へプルリクエストを提出します。
    5.  頂いたコメントやレビューからの提案で、更に内容を変更する場合は、
        自分のブランチで内容を変更し、GitHubのフォークにプッシュして下さい：
        自動的にプルリクエストの内容がアップデートされます。

全てのレッスンには二人のメインテイナーがおり、彼・彼女らがイシューやプルリクエストを管理・見直す、
もしくはその他のメンバーに、一緒に見直すように声をかけます。
メインテイナー達はコミュニティーのボランティアですので、
最終的に何を変更するかの決定権は、メインテイナーに委ねられています。

## その他の資料

[Software Carpentry][swc-site]と[Data Carpentry][dc-site]についての一般的なディスカッションは、
[ディスカッション用のメーリングリスト][discuss-list]で行われ、
どなたでも参加できます。
また、[メール][contact]からでもご連絡いただけます。

[contact]: mailto:team@carpentries.org
[dc-issues]: https://github.com/issues?q=user%3Adatacarpentry
[dc-lessons]: http://datacarpentry.org/lessons/
[dc-site]: http://datacarpentry.org/
[discuss-list]: https://carpentries.topicbox.com/groups/discuss
[github]: https://github.com
[github-flow]: https://guides.github.com/introduction/flow/
[github-join]: https://github.com/join
[how-contribute]: https://egghead.io/series/how-to-contribute-to-an-open-source-project-on-github
[new-issue]: https://github.com/swcarpentry/r-novice-gapminder/issues/new
[issues]: https://github.com/swcarpentry/r-novice-gapminder/issues/
[repo]: https://github.com/swcarpentry/r-novice-gapminder/
[swc-issues]: https://github.com/issues?q=user%3Aswcarpentry
[swc-lessons]: https://software-carpentry.org/lessons/
[swc-site]: https://software-carpentry.org/

