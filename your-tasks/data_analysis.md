## **データ分析のベストプラクティスは何か？**

### **概要**

分析を行う際には、すべてのデータ分析が再現可能でなければならないことを念頭に置く必要があります。これは、データが<span>FAIR</span>に準拠しているだけでなく、ツールや分析環境も含めた研究データ管理のアプローチを補完するものです。言い換えれば、結果を出すために、どのデータをどのようなコードやツールで使用したかがわかるようにしておく必要があります。

これにより、再現性の問題に取り組むことができるだけでなく、コンピュータを用いて行う実験を再現する科学者との共同研究を通じて、研究のインパクトを向上させることができます。

### **考察**

データ分析を再現可能にする方法は複数存在します。実施方法は、いくつかのレベルに分かれています：

* コードの提供
* 実行環境の提供
* ワークフローの提供
* データ分析を実行した結果の提供

### **ソリューション**

* 自分のコードを利用可能にしてください。データ分析のために何らかのソフトウェアを開発しなければならない場合、コードを公開することは常に良いアイデアです。<span>Git</span>は、コードを公開する方法だけでなく、バージョン管理システムも提供しています。また、<span>Git上では</span>ソフトウェア開発者と対話することもできます。その場合、コードのライセンスを必ず指定してください（「ライセンス」の項をご覧ください）。
* パッケージや実行環境の管理システムを使用してください。[<span>Conda</span>](https://anaconda.org/)やそのバイオインフォマティクス専門チャンネルである[<span>Bioconda</span>](https://bioconda.github.io/)のようなパッケージや実行環境の管理システムを使用することで、あなたのコードにアクセスした研究者は、特定のバージョンのツールを簡単にインストールすることができ、古いものであっても隔離された環境で使用することができます。研究者は、あなたのコードを、正しいバージョンの<span>R</span>や、あなたのコードが使用する特定のライブラリやコマンドラインツールなどの依存関係を含めて、同様の計算環境でコンパイル<span>/</span>実行することができます。また、どのツールをインストールしたかを環境ファイルで指定することで、セットアップを共有・保存することができます。
* コンテナ環境を利用してください。パッケージ管理システムの代わりに、[<span>Docker</span>](https://www.docker.com/)や[<span>Singularity</span>](https://sylabs.io/docs/)のようなコンテナ環境を検討することができます。
* ワークフロー管理システムを使用してください。[科学的ワークフロー管理システム](https://en.wikipedia.org/wiki/Scientific_workflow_system)は、計算ツールの実行方法を整理し、自動化するのに役立ちます。独立したスクリプトを使ってツールを構成する場合と比較して、ワークフローシステムは、データに適用されるさまざまな計算分析を文書化するのにも役立ち、クラウド実行などのスケーラビリティにも役立ちます。また、ワークフローには、ソフトウェアパッケージを指定するためのバインディングや、ワークフローで使用するツールのためのコンテナが用意されており、必要なソフトウェアをすべて事前にインストールしなくても、他の人がワークフローを再実行することができるため、再現性も高まります。この分野は盛んで、他にも多くのワークフロー管理システムがあり、その中には汎用的なもの（例：任意のコマンドラインツール）もあれば、ドメインに特化し、より緊密なツール統合を行うものもあります。[数多くのワークフロー管理システム](https://s.apache.org/existing-workflow-systems)の中で、以下のものを挙げることができます。

  * データを管理し、複雑なパイプラインを実行してその結果を確認するためのインターフェイス（ウェブ、<span>GUI</span>、<span>API</span>）を提供するワークフロープラットフォーム。例えば、[<span>Galaxy</span>](https://galaxyproject.org/)や[<span>Arvados</span>](https://arvados.org/)（<span>CWL</span>ベース、オープンソース）が挙げられます。
  * 独自形式または標準形式（[<span>CWL</span>規格](https://www.commonwl.org/)など）で記述されたワークフローを取り込み、ローカルまたはリモートの計算インフラで実行するワークフローランナー。例えば、[<span>toil-cwl-runner</span>](https://toil.readthedocs.io/en/latest/running/cwl.html)、リファレンス<span>CWL</span>ランナー（[<span>cwltool</span>](https://pypi.org/project/cwltool/)）、[<span>Nextflow</span>](https://www.nextflow.io/)、[<span>Snakemake</span>](https://snakemake.readthedocs.io/)、[<span>Cromwell</span>](https://cromwell.readthedocs.io/)などが挙げられます。
* ノートブックを使用してください。ノートブックを使用すると、テキストとコードを組み合わせた再現性のある文書を作成することができます。この文書は、分析の選択肢を説明するのに役立つだけでなく、データを詳細に調査するための探索的な方法としても使用できます。ノートブックは、上記の他のソリューションと組み合わせて使用することができ、通常、ノートブックをスクリプトに変換することができます。よく知られているノートブックシステムには次のようなものがあります：[<span>Jupyter</span>](https://jupyter.org/)は、<span>Python</span>、<span>R</span>、<span>Julia</span>、その他多くのカーネルのコードをサポートしています。また、<span>R</span>をベースにした[<span>RStudio</span>](https://rstudio.com/products/rstudio/#rstudio-desktop)もあります。

## **パッケージや実行環境の管理システムはどのように利用できるのか？**

### **概要**

[Conda](https://anaconda.org/)やバイオインフォマティクスに特化した[<span>Bioconda</span>](https://bioconda.github.io/)のような、パッケージや実行環境の管理システムを使用することで、特定のバージョンのツールや古いツールを隔離された環境に簡単にインストールすることができます。また、どのツールをインストールしたかを環境ファイルで指定することで、セットアップを共有・保存することができます。

### **考察**

Condaは、伝統的な<span>UNIX</span>のディレクトリ構造である<span>bin/lib/</span>を含むネストしたフォルダを作成して動作しますが、<span>Linux</span>ディストリビューションからではなく、<span>Conda</span>のリポジトリからインストールされます。

* そのため、<span>Conda</span>は、ディストリビューションや<span>OS</span>のバージョンに依存しない、計算ツールの一貫したインストールを可能にします。<span>Conda</span>は、<span>Linux</span>、<span>macOS</span>、<span>Windows</span>に対応しており、<span>OS</span>を問わず一貫した操作性を提供します（ただし、すべてのソフトウェアがすべての<span>OS</span>に対応しているわけではありません）。
* パッケージ管理システムは、特にフリーソフトウェアやオープンソースソフトウェアのインストールに適していますが、商用ソフトウェアのパッケージをインストールする際に隔離された環境を構築するのにも役立ちます。例えば、商用パッケージが、プリインストールされているよりも古いバージョンのPythonを必要とする場合などです。
* Condaは一般的なパッケージ管理の一例ですが、個々のプログラミング言語は通常、それぞれの実行環境管理とパッケージを行うためのリポジトリを持っています。
* 自分のコード自体、あるいは少なくともその一般的な部分を、自分のプログラミング言語のパッケージリポジトリへ登録することを検討するとよいでしょう。

**ソリューション**

* MacOS固有のパッケージ管理システム：<span>[Homebrew](https://brew.sh/)、[Macports](https://www.macports.org/)</span>
* Windows固有のパッケージ管理システム：[<span>Chocolatey</span>](https://chocolatey.org/)、<span>[Windows Package Manager (winget)](https://docs.microsoft.com/en-us/windows/package-manager/) </span>
* Linux ディストリビューションにも独自のパッケージ管理システム<span> (rpm/yum/dnf, deb/apt) </span>があり、さまざまなツールが利用できますが、その代わりにツールのバージョンに関する柔軟性が低いため、全て一緒にインストールされている必要があります。
* 言語固有の仮想環境やリポジトリ：<span>Ruby</span>には[<span>rvm</span>](https://rvm.io/)や[<span>RubyGems</span>](https://rubygems.org/)、<span>Python</span>には[<span>pip</span>](https://docs.python.org/3/installing/index.html)や[<span>venv</span>](https://docs.python.org/3/tutorial/venv.html)、<span>NodeJS/Javascript</span>には[<span>npm</span>](https://www.npmjs.com/)、<span>R</span>には[<span>renv</span>](https://rstudio.github.io/renv/)や[<span>CRAN</span>](https://cran.r-project.org/)、<span>Java</span>には[<span>Apache Maven</span>](https://maven.apache.org/)や[<span>Gradle</span>](https://gradle.org/)などがあります。
* ソフトウェアパッケージ管理を使いこなすためのヒントやコツを紹介します：

  * OSから独立して必要なソフトウェアを管理してください。ソフトウェアを実行するための<span>OS</span>タイプやバージョンが、作業環境と異なる場合は、<span>Conda の environment.yml</span>にパッケージをリストアップします。
  * <span>OSやバージョンが異なる環境において、ツール/ライブラリのいくつかで、相反するバージョンが必要な場合、別々のConda環境を作成してください。</span>
  * Pythonスクリプトのためにいくつかのオープンソースライブラリが必要で、どれもコンパイルを必要としない場合、<span>requirements.txt</span>を作成して<span>pip</span>パッケージをリストアップしてください。

## **コンテナ環境はどうやって使うのか？**

### **概要**

[Docker](https://www.docker.com/)や[<span>Singularity</span>](https://sylabs.io/docs/)のようなコンテナ環境では、特定のバージョンのツールを、古いものでも簡単に隔離された環境にインストールすることができます。

### **考察**

コンテナは、プロセス、ファイル、ネットワークを分離して、<span>Linux</span>のディスク全体を再現するという点で、仮想マシン（<span>VM</span>）とほぼ同じ働きをします。

* コンテナは、ハードウェアを仮想化しないため、<span>VM</span>よりも軽量です。これにより、コンテナはホストに依存しない固定バージョンのディストリビューションで動作し、適切かつ最小限の依存関係でインストールすることができます。
* また、コンテナを隔離することで、<span>VM</span>ほど安全ではないものの、攻撃経路（attack vector）を減らすことができます。例えば、データベースコンテナが好ましくない訪問者によって侵害された場合、その訪問者はウェブサーバの設定を変更することができず、コンテナは追加のサービスをインターネットに公開することができません。
* コンテナの大きな利点は、コミュニティが提供するコンテナイメージの大規模なレジストリが存在することです。
* <span>コンテナ内部を書き換えることは通常のマシンに比べて注意が必要です。コンテナを作り直すと修正が失われてしまいます。</span>
* 通常、コンテナは<span>1</span>つのツールやアプリケーションだけを実行します。サービスのデプロイメントでは、例えば、<span>NodeJS</span>アプリケーションとは別のコンテナで<span>mySQL</span>データベースを実行するのが便利です。

### **ソリューション**

* コンテナランタイムとしては、[<span>Docker</span>](https://www.docker.com/)が最も有名で、次いで[<span>Singularity</span>](https://sylabs.io/docs/)が挙げられます。これらは、システム管理者の権限を設定する必要があります。
* [uDocker](https://indigo-dc.gitbook.io/udocker/)と[<span>Podman</span>](https://podman.io/)も、Dockerの代替として利用できます。どちらも、コマンドラインに対応したユーザースペースを提供します。
* コミュニティが提供するコンテナイメージの大規模な登録機関としては、[<span>Docker Hub</span>](https://hub.docker.com/)と[<span>RedHat Quay.io</span>](https://quay.io/search)があります。これらは多くの場合、追加の設定やインストールを必要とせず、すぐに使える状態になっているので、アプリケーションはすぐにオープンソースのサーバソリューションにアクセスすることができます。
* [Biocontainers](https://biocontainers.pro/)には、バイオインフォマティクスのツールが多数用意されています。
* Dockerイメージをカスタマイズするために、データを保存する[Volume](https://docs.docker.com/storage/volumes/)や[<span>Dockerfile</span>](https://docs.docker.com/engine/reference/builder/)などの技術を使用することが可能です。これらの技術は、自分のアプリケーションを新しいコンテナイメージ内にインストールする際に便利です。<span>apt install</span>やソフトウェアのセットアップを再現性のある方法で行うことができる適切なベースイメージを基にして、自分のアプリケーションをimageファイルとして<span>Docker Hub</span>で共有することができます。
* コンテナの連携は、[<span>Docker Compose</span>](https://docs.docker.com/compose/)のようなツールを使ったコンテナコンポジションで行うことができます。
* [Kubernetes](https://kubernetes.io/)や科学的ワークフロー管理システムのような、より高度なコンテナ展開ソリューションでは、クラウドのインスタンスを管理したり、分析に利用することもできます。
* コンテナソリューションの状況をナビゲートするためのヒントとコツを挙げます：

  * <span>データベースサーバを動かすだけなら、それをDocker/Singularityコンテナで、どう動かすかを記述してください。</span>
  * 複数のサーバーを稼働させ、接続する必要がある場合は、<span>Docker Compose</span>でコンテナをセットアップしてください。
  * 多くのものをインストールする必要があり、その中にはパッケージとして利用できないものもある場合、コンテナイメージを構築するために新しい<span>Dockerfile</span>レシピを作成してください。
  * パイプラインで複数のツールを使用する必要がある場合、<span>Conda</span>やコンテナイメージを見つけて、それらを科学的ワークフローで構成してください。
  * クラウドインスタンスでツールを実行する必要がある場合、何もプリインストールされていなければ、<span>Conda</span>またはコンテナを使用してインストールを行い、クラウド上のインストール結果がローカルマシンと一致するようにしてください。
  * [ImageMagick](https://imagemagick.org/index.php) などの特定のオープンソースツールをインストールする必要がある場合は、インストール方法のドキュメントを確認してください。<span>Ubuntu 20.04 </span>の場合は、<span>apt install imagemagick </span>を実行してください。