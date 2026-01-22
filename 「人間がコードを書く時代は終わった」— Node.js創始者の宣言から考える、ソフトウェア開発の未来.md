
![](https://storage.googleapis.com/zenn-user-upload/0066bbe6772e-20260121.png)
「人間がコードを書く時代は終わった」

この言葉は、Node.jsの生みの親であるRyan Dahlが最近投稿したツイートの一節です。彼はこう続けています。「SWE（ソフトウェアエンジニア）を自認する私たちにとっては不穏な話だが、それでも真実だ。エンジニアの仕事がなくなるわけではない。ただ、シンタックスを直接書くことはもう仕事ではなくなった」

私自身、Claude Codeを使い始めてから半年が経ちました。振り返ってみると、この間ほとんど手でコードを書いていません。最初は「本当にこれでいいのか」という不安がありましたが、今では全く違う形でソフトウェア開発と向き合っています。

この記事では、著名な開発者たちの見解を整理しながら、AIコーディング時代に私たちエンジニアがどう生き残るべきかを考えてみます。

---

## [](https://zenn.dev/liushengli/articles/c12d4a6881b604#%E8%91%97%E5%90%8D%E9%96%8B%E7%99%BA%E8%80%85%E3%81%9F%E3%81%A1%E3%81%AE%E8%A6%8B%E8%A7%A3-%E2%80%94-%E6%A5%BD%E8%A6%B3%E6%B4%BE%E3%82%82%E6%87%90%E7%96%91%E6%B4%BE%E3%82%82%E8%AA%8D%E3%82%81%E3%82%8B%E7%8F%BE%E5%AE%9F)著名開発者たちの見解 — 楽観派も懐疑派も認める現実

### [](https://zenn.dev/liushengli/articles/c12d4a6881b604#ryan-dahl%E3%81%AE%E5%AE%A3%E8%A8%80)Ryan Dahlの宣言

Ryan Dahlは、2009年にJSConf EUでNode.jsを発表し、スタンディングオベーションを受けた伝説的なエンジニアです。その後、Node.jsの「10の後悔」を語り、Denoという新しいランタイムを作り上げた人物でもあります。

そんな彼が「コードを書く時代は終わった」と言うのですから、これは単なるハイプではありません。彼の個人ブログ（tinyclouds.org）では、「人間は確率的オウムに過ぎない」「AIの意味をまだ過小評価している」といった記事も公開されています。

_出典: [The era of humans writing code is over](https://x.com/rough__sea/status/2013280952370573666?ref_src=twsrc%5Etfw%7Ctwcamp%5Etweetembed%7Ctwterm%5E2013280952370573666%7Ctwgr%5E%7Ctwcon%5Es1_&ref_url=)_

### [](https://zenn.dev/liushengli/articles/c12d4a6881b604#dhh%E3%81%AE%E5%AE%9F%E8%B7%B5%E7%9A%84%E3%81%AA%E6%87%90%E7%96%91%E8%AB%96)DHHの実践的な懐疑論

Ruby on Railsの創始者であるDHH（David Heinemeier Hansson）は、もっと慎重な立場を取っています。彼はAIツールを「点滅する電球」に例えました。時々役立つ光を放つが、しばしば開発者を暗闇に置き去りにする、と。

「毎日AIに『このコードを書いてくれ』と頼んでいる。そしてAIは書く。でも出てきたコードを見て『これはメンテナンスしたくない。ほとんどのジュニア開発者より質が低い』と思うことが多い」

ただし、DHHの見解も変化しています。2025年7月のLex Fridmanのポッドキャストでは、「以前より懐疑的ではなくなった」と認めています。彼はCursorをダウンロードし、コードを一切手で打たずにプロジェクト全体を構築する実験を行いました。そして「AIのおかげでようやくペアプログラミングを楽しめるようになった。私は内向的だから、以前は5分で橋から飛び降りたくなっていた」と冗談交じりに語っています。

### [](https://zenn.dev/liushengli/articles/c12d4a6881b604#kent-beck%E3%81%AE%E3%80%8C90%25%E3%81%A810%25%E3%80%8D)Kent Beckの「90%と10%」

Extreme Programming（XP）の提唱者であり、テスト駆動開発（TDD）のパイオニアでもあるKent Beckは、2023年に衝撃的なツイートを投稿しました。

> 「私のスキルの90%の価値が$0になった。残りの10%のレバレッジが1000倍になった。再調整が必要だ」

そして2年後、彼はこの発言を振り返り、**価値ある10%のスキル**が何かを具体的に説明しています。

---

## [](https://zenn.dev/liushengli/articles/c12d4a6881b604#%E4%BE%A1%E5%80%A4%E3%81%8C1000%E5%80%8D%E3%81%AB%E3%81%AA%E3%82%8B%E3%80%8C10%25%E3%81%AE%E3%82%B9%E3%82%AD%E3%83%AB%E3%80%8D%E3%81%A8%E3%81%AF)価値が1000倍になる「10%のスキル」とは

Kent Beckによれば、価値を失った90%は**合成スキル**（ゼロから解決策を生み出す能力）であり、価値が爆発的に上がった10%は**分析スキル**（問題と解決策を分析する能力）です。

具体的には以下のスキルが挙げられています。

### [](https://zenn.dev/liushengli/articles/c12d4a6881b604#1.-%E3%83%93%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%92%E6%8F%8F%E3%81%8F%E5%8A%9B)1. ビジョンを描く力

何を作るべきか、どこに向かうべきかを明確に描く能力。AIは指示されたことを実行できますが、「そもそも何を作るべきか」を決めることはできません。

### [](https://zenn.dev/liushengli/articles/c12d4a6881b604#2.-%E3%83%9E%E3%82%A4%E3%83%AB%E3%82%B9%E3%83%88%E3%83%BC%E3%83%B3%E8%A8%AD%E8%A8%88)2. マイルストーン設計

ビジョンに向けた段階的な目標を設定する能力。大きな目標を適切なサイズのタスクに分解し、優先順位をつけることは依然として人間の仕事です。

### [](https://zenn.dev/liushengli/articles/c12d4a6881b604#3.-%E8%A4%87%E9%9B%91%E6%80%A7%E3%81%AE%E3%82%B3%E3%83%B3%E3%83%88%E3%83%AD%E3%83%BC%E3%83%AB)3. 複雑性のコントロール

設計を維持し、システムの複雑さを管理する能力。Kent Beckは「Rustの&と*と括弧をどこに置くか知っていることより、設計を前進させながら複雑性を制御することの方がはるかにレバレッジが高い」と述べています。

### [](https://zenn.dev/liushengli/articles/c12d4a6881b604#4.-%E5%A5%87%E5%A6%99%E3%81%AA%E3%82%A2%E3%83%8A%E3%83%AD%E3%82%B8%E3%83%BC%E3%82%92%E8%A6%8B%E3%81%A4%E3%81%91%E3%82%8B%E5%8A%9B)4. 奇妙なアナロジーを見つける力

誰も思いつかないような接続を作る能力。これは創造性の核心であり、AIが最も苦手とする領域です。

### [](https://zenn.dev/liushengli/articles/c12d4a6881b604#5.-%E5%88%A4%E6%96%AD%E5%8A%9B%EF%BC%88judgment%EF%BC%89)5. 判断力（Judgment）

「コードは豊富、判断力は希少。希少な存在になれ」という言葉が端的に表しています。AIは常に答えを出しますが、人間は「答えを出さないほうがいい時」を知っています。AIには結果に対する感覚がありません。何ができるかは分かりますが、何をすべきかは分かりません。

### [](https://zenn.dev/liushengli/articles/c12d4a6881b604#6.-%E6%89%B9%E5%88%A4%E7%9A%84%E6%80%9D%E8%80%83)6. 批判的思考

MicrosoftとCMUの研究によれば、AIツールの使用頻度が上がるほど、開発者自身の問題解決能力は低下します。だからこそ、AIの出力を批判的に評価する能力がますます重要になります。

![Vibe Codingのワークフロー](https://res.cloudinary.com/zenn/image/fetch/s--I2PNsMaa--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_1200/https://dx1ienyxpbg1x.cloudfront.net/index_dev/articles/gallery_images/1742827066797412245_3_The%2520Rise%2520of%2520Vibe%2520Coding_%2520How%2520AI%2520is%2520Changing%2520Development_blog%2520image_3.png?_a=BACAGSGT)_出典: [Index.dev - How Vibe Coding is Changing Software Development](https://www.index.dev/blog/vibe-coding-ai-development)_

---

## [](https://zenn.dev/liushengli/articles/c12d4a6881b604#vibe-coding%E3%81%8B%E3%82%89spec-driven-development%E3%81%B8)Vibe CodingからSpec-Driven Developmentへ

### [](https://zenn.dev/liushengli/articles/c12d4a6881b604#vibe-coding%E3%81%A8%E3%81%AF)Vibe Codingとは

「Vibe Coding」という言葉は、2025年2月にOpenAIの共同創業者Andrej Karpathyによって提唱されました。自然言語でAIに指示を出し、AIがコードを生成する開発スタイルのことです。驚くべきことに、この言葉は2025年のCollins英語辞典「Word of the Year」に選ばれました。

2025年春には「Vibe Coding」の検索が6,700%も急増。McKinseyの調査では、62%の組織が自律的なAI「コーディングエージェント」を試験導入しています。グローバルで見ると、コードの41%がすでにAI生成であり、Javaプロジェクトではその数字は61%にまで達しています。

### [](https://zenn.dev/liushengli/articles/c12d4a6881b604#vibe-coding%E3%81%AE%E9%99%90%E7%95%8C)Vibe Codingの限界

しかし、Vibe Codingには明確な限界があります。

CodeRabbitの調査によると、AIで開発者は確かに速くなりましたが、その恩恵は欠陥のあるコードの修正やセキュリティ問題への対処に費やす時間で相殺されています。AIが生成したPRは、人間が書いたものより**1.4倍多くのクリティカルな問題**、**1.7倍多くのメジャーな問題**を含んでいるという報告もあります。

興味深いことに、開発者の84%がAIツールを使用または使用予定である一方、AIの出力を**積極的に信頼しない**開発者は47%に上昇しています（2024年は31%でした）。

### [](https://zenn.dev/liushengli/articles/c12d4a6881b604#spec-driven-development%EF%BC%88%E4%BB%95%E6%A7%98%E9%A7%86%E5%8B%95%E9%96%8B%E7%99%BA%EF%BC%89%E3%81%AE%E5%8F%B0%E9%A0%AD)Spec-Driven Development（仕様駆動開発）の台頭

こうした状況を受けて、2025年後半から注目されているのが**Spec-Driven Development（SDD）**です。

SDDは、よく練られた仕様書をプロンプトとして使用し、AIエージェントに実行可能なコードを生成させる開発パラダイムです。GitHubがオープンソースで公開した「Spec Kit」は、Claude Code、GitHub Copilot、Gemini CLIなどのツールと連携して、この手法を実践できるようにしています。

OpenAIのSean Groveは次のように述べています。「未来で最も価値のあるプログラマーは、最もうまくコミュニケーションできる人だ。新しい希少スキルは、意図と価値観を完全に捉える仕様を書くことだ」

![従来の開発とVibe Codingの効率比較](https://res.cloudinary.com/zenn/image/fetch/s--V_Fuq-QE--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_1200/https://dx1ienyxpbg1x.cloudfront.net/index_dev/articles/gallery_images/1742827095969686087_5_The%2520Rise%2520of%2520Vibe%2520Coding_%2520How%2520AI%2520is%2520Changing%2520Development_blog%2520image_2.png?_a=BACAGSGT)

_出典: [Index.dev - How Vibe Coding is Changing Software Development](https://www.index.dev/blog/vibe-coding-ai-development)_

---

## [](https://zenn.dev/liushengli/articles/c12d4a6881b604#%E7%AD%86%E8%80%85%E3%81%AE%E5%AE%9F%E4%BD%93%E9%A8%93-%E2%80%94-claude-code%E3%81%A8%E9%81%8E%E3%81%94%E3%81%97%E3%81%9F%E5%8D%8A%E5%B9%B4)筆者の実体験 — Claude Codeと過ごした半年

私自身、Claude Codeを使い始めてから約半年が経ちました。その間の経験を正直に振り返ってみます。

### [](https://zenn.dev/liushengli/articles/c12d4a6881b604#%E7%94%9F%E7%94%A3%E6%80%A7%E3%81%AF%E7%A2%BA%E5%AE%9F%E3%81%AB%E5%90%91%E4%B8%8A%E3%81%97%E3%81%9F)生産性は確実に向上した

これは間違いありません。以前なら数日かかっていた機能実装が、数時間で完了するようになりました。特にボイラープレートコードの生成、APIの統合、テストケースの作成などは、AIに任せることで劇的に効率化されました。

あるGoogleのプリンシパルエンジニアは「分散エージェントオーケストレーターを1年かけて構築しようとしていた。Claude Codeに問題を説明したら、1時間で同等のものを生成した」と報告しています。これは極端な例かもしれませんが、私も似たような体験を何度もしています。

### [](https://zenn.dev/liushengli/articles/c12d4a6881b604#%E3%81%97%E3%81%8B%E3%81%97%E3%80%81%E5%95%8F%E9%A1%8C%E3%82%82%E5%A4%9A%E3%81%84)しかし、問題も多い

AIが書くコードは「動く」けれど「良い」とは限りません。一見きれいに見えるコードでも、エッジケースの考慮が甘かったり、セキュリティホールがあったり、長期的なメンテナンス性を考慮していなかったりします。

LLMは「ハルシネーション」を起こしやすいという問題は構造的なものであり、コーディングでも例外ではありません。出力がプロフェッショナルに見えるだけに、エラーを見つけるのが難しいのです。

### [](https://zenn.dev/liushengli/articles/c12d4a6881b604#vibe-coding%E3%81%8B%E3%82%89spec-driven-dev%E3%81%B8%E3%81%AE%E9%80%B2%E5%8C%96)Vibe CodingからSpec-Driven Devへの進化

最初はまさに「Vibe Coding」でした。思いついたことをAIに投げて、出てきたコードをそのまま使う。でも、プロジェクトが大きくなるにつれて破綻しました。

今では、AIに何かを依頼する前に、まず仕様を明確にするようになりました。何を作りたいのか、どういう制約があるのか、どんなエッジケースを考慮すべきか。これを明文化してからAIに渡すと、出力の質が格段に上がります。

ただし、ここで重要なのは、**仕様を最初から完璧に自分で書く必要はない**ということです。私のやり方は、まず大まかなアイデアや方向性だけを持った状態でAIとの対話を始めます。「こういうものを作りたいんだけど、どういう仕様にすべきだと思う？」とAIに問いかけ、返ってきた提案に対して「いや、ここはこうしたい」「このケースはどう扱う？」と議論を重ねていく。何往復かのやり取りを経て、ようやく詳細な仕様が固まります。つまり、**仕様策定そのものがAIとの共同作業**なのです。

### [](https://zenn.dev/liushengli/articles/c12d4a6881b604#%E3%80%8C%E8%A8%AD%E8%A8%88%E8%80%85%E3%80%8D%E3%81%A8%E3%81%97%E3%81%A6%E3%81%AE%E8%87%AA%E5%88%86%E3%81%AE%E5%86%8D%E7%99%BA%E8%A6%8B)「設計者」としての自分の再発見

面白いのは、コードを書かなくなったことで、逆に「設計」について深く考えるようになったことです。Stripeのエンジニアが言っていた「コードを書くことから、アーキテクト、プロダクトマネージャーのような存在になりつつある」という感覚は、私にもよく分かります。

---

## [](https://zenn.dev/liushengli/articles/c12d4a6881b604#2026%E5%B9%B4%E4%BB%A5%E9%99%8D%E3%80%81%E3%82%A8%E3%83%B3%E3%82%B8%E3%83%8B%E3%82%A2%E3%81%AF%E3%81%A9%E3%81%86%E3%81%AA%E3%82%8B%E3%81%8B)2026年以降、エンジニアはどうなるか

### [](https://zenn.dev/liushengli/articles/c12d4a6881b604#%E3%80%8C%E3%82%B3%E3%83%BC%E3%83%80%E3%83%BC%E3%80%8D%E3%81%8B%E3%82%89%E3%80%8C%E3%82%AA%E3%83%BC%E3%82%B1%E3%82%B9%E3%83%88%E3%83%AC%E3%83%BC%E3%82%BF%E3%83%BC%E3%80%8D%E3%81%B8)「コーダー」から「オーケストレーター」へ

2026年のソフトウェアアーキテクトにとって最も価値のあるスキルは、完璧なコードを書くことではありません。それは、コードを書いてくれる自律的なAIエージェントをオーケストレーション（指揮）することです。

GitLabの予測によれば、75%以上の開発者が「構築」ではなく「設計・統治・オーケストレーション」に従事するようになります。WarpのCEO、Zach Lloydはこう述べています。「2025年はAIが開発者を置き換える年になるはずだった。でも全然そうならなかった。実際に起きたのは、開発者がAIエージェントのオーケストレーターになったということだ」

### [](https://zenn.dev/liushengli/articles/c12d4a6881b604#%E4%BA%BA%E9%96%93%E3%81%AE%E7%9B%A3%E8%A6%96%E3%81%8C%E4%B8%8D%E5%8F%AF%E6%AC%A0%E3%81%AA%E7%90%86%E7%94%B1)人間の監視が不可欠な理由

AIには結果に対する感覚がありません。待つべき時でも、常に答えを出そうとします。一方、人間には直感、判断力、道徳的文脈があります。「何ができるか」だけでなく「何をすべきか」を考えられるのです。

現時点では、どんなプロジェクトであれ、人間の監視なしにAIだけで開発を完結させることは現実的ではありません。AIが生成するコードには必ずレビューが必要であり、アーキテクチャの決定、ビジネスロジックの妥当性、セキュリティの担保は人間が責任を持つ領域です。AIは強力なアシスタントですが、最終的な判断と責任は常に人間にあります。

### [](https://zenn.dev/liushengli/articles/c12d4a6881b604#%E6%96%B0%E3%81%97%E3%81%84%E3%82%B9%E3%82%AD%E3%83%AB%E3%82%BB%E3%83%83%E3%83%88)新しいスキルセット

2026年以降のエンジニアに求められるスキルは明確に変化しています。

- **AIオーケストレーション**: AIがリアルタイムデータ、内部データベース、外部APIと連携するシステムを構築する能力
    
- **システム設計**: AIがルーチン作業を担う分、スケーラブルで保守可能なシステムを設計する能力の重要性が増している
    
- **批判的コードレビュー**: 2026年の開発者のスキルは、QuickSortを書くことではなく、AIが生成したQuickSortを見て「不安定なピボットを使っている」と即座に見抜くこと
    
- **ソフトスキル**: 感情的知性、倫理的推論、ビジネスニーズと技術実装の橋渡し
    

---

## [](https://zenn.dev/liushengli/articles/c12d4a6881b604#%E3%81%BE%E3%81%A8%E3%82%81-%E2%80%94-%E5%B8%8C%E5%B0%91%E3%81%AA%E5%AD%98%E5%9C%A8%E3%81%AB%E3%81%AA%E3%82%8B%E3%81%9F%E3%82%81%E3%81%AB)まとめ — 希少な存在になるために

「コードは豊富、判断力は希少。希少な存在になれ」

これは今の状況を端的に表している言葉です。AIがコードを大量生産できる時代に、「平均的な仕事」を簡単に生成できるようになりました。だからこそ、判断力こそが最も価値のあるスキルになります。

人間がコードを書く時代は本当に終わりつつあるのかもしれません。でも、それは開発者の仕事がなくなることを意味しません。むしろ、私たちは「総設計師」として、AIが生成するものの方向性を決め、品質を担保し、最終的な責任を負う存在として、これまで以上に重要な役割を担うことになります。

激動の進化の真っ只中にいる今、将来がどうなるかは正直分かりません。ただ一つ確かなのは、変化を恐れるのではなく、自分のスキルセットを「再調整」し続けることが、生き残りの鍵だということです。

Kent Beckが言った「再調整が必要だ」という言葉は、すべてのエンジニアに向けられた呼びかけなのかもしれません。

---

## [](https://zenn.dev/liushengli/articles/c12d4a6881b604#%E5%8F%82%E8%80%83%E8%B3%87%E6%96%99)参考資料

- [Ryan Dahl's Personal Blog - tinyclouds.org](https://tinyclouds.org/)
    
- [Medium - The creator of Node.js says the era of writing code is over](https://jpcaparas.medium.com/the-creator-of-node-js-says-the-era-of-writing-code-is-over-8320c868043b)
    
- [Kent Beck - 90% of My Skills Are Now Worth $0](https://tidyfirst.substack.com/p/90-of-my-skills-are-now-worth-0)
    
- [Simon Willison - A quote from Kent Beck](https://simonwillison.net/2025/Jun/22/kent-beck/)
    
- [MIT Technology Review - AI coding is now everywhere](https://www.technologyreview.com/2025/12/15/1128352/rise-of-ai-coding-developers-2026/)
    
- [The New Stack - AI Engineering Trends in 2025](https://thenewstack.io/ai-engineering-trends-in-2025-agents-mcp-and-vibe-coding/)
    
- [GitHub Blog - Spec-driven development with AI](https://github.blog/ai-and-ml/generative-ai/spec-driven-development-with-ai-get-started-with-a-new-open-source-toolkit/)
    
- [Thoughtworks - Spec-driven development](https://www.thoughtworks.com/en-us/insights/blog/agile-engineering-practices/spec-driven-development-unpacking-2025-new-engineering-practices)
    
- [Index.dev - How Vibe Coding is Changing Software Development](https://www.index.dev/blog/vibe-coding-ai-development)
    
- [DEV Community - The 2026 Architect's Dilemma](https://dev.to/ridwan_sassman_3d07/the-2026-architects-dilemma-orchestrating-ai-agents-not-writing-code-the-paradigm-shift-from-219c)
    
- [Builder.io - The AI software engineer in 2026](https://www.builder.io/blog/ai-software-engineer)
    
- [GeekWire - Claude Code has Seattle engineers buzzing](https://www.geekwire.com/2026/a-new-era-of-software-development-claude-code-has-seattle-engineers-buzzing-as-ai-coding-hits-new-phase/)