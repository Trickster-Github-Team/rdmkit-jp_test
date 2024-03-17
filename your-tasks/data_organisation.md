## **ファイルに名前を付ける最良の方法は？**

### **概要**

簡潔で中身が分かるファイル名は、データファイルを整理する上で重要です。ファイル名は、ファイルの主要な識別子であり、良い名前は、ファイルに何が含まれているかを示し、ファイルの分類に役立ちます。

### **考察**

* ベストプラクティスは、プロジェクトの開始時に、プロジェクトにとって重要な要素を含むファイル命名規則を作成することです。
* 他の人と共同で作業する場合は、同じファイル命名規則を設定することが重要です。

### **ソリューション**

**ファイル名の付け方のポイント**

* 構成要素数とのバランスを取ってください：多すぎるとわかりにくく、少なすぎると一般的になります。
* 一般的な要素から具体的な要素へと順番に並べてください。
* 意味のある略語を使ってください。
* アンダースコア<span>(_)</span>、ハイフン<span>(-)</span>、または大文字を使って、名前の中の要素を分離してください。<span>スペースや次に示すような特殊文字を使ってはいけません：</span><span> ?!& , * % # ; * ( ) @$ ^ ~ ' { } [ ] < >. [ ] < >.</span>
* 日付は<span>ISO8601</span>を使用してください：日付は<span>YYYYMMDD</span>、必要に応じて、時間は<span>HHMMSS</span>を使用してください。
* 必要に応じて、バージョン番号を記載してください：最小<span>2</span>桁（<span>V02</span>）で、マイナーな修正が必要な場合は拡張します（<span>V02-03</span>）。先頭のゼロは、ファイルが正しくソートされるようにするためです。
* ファイルの命名規則を書き留め、略語はデータの説明書に記載してください。
* プロジェクトデータの整理やファイルの管理を容易にするために、多くのファイル名を変更する必要がある場合は、[<span>Bulk Rename Utility</span>](https://www.bulkrenameutility.co.uk/)（<span>Windows</span>、無料）や[<span>Renamer4Mac</span>](https://renamer.com/)（<span>Mac</span>）などのアプリケーションを使用することができます。

**ファイル名に含まれる要素例**

* 作成日
* プロジェクト番号／実験／頭文字
* データの種類（サンプル<span>ID</span>、分析、状態、修正など）
* 位置／座標
* 名前／作成者のイニシャル
* バージョン番号
* 最後の<span>3</span>文字はファイル形式（例：<span>.xls</span>、<span>.rtf</span>、<span>.mov</span>、<span>.tif</span>、<span>.doc</span>）になります。

**良いファイル名の例**

* Honeybeeプロジェクト、ヘルシンキで行われた実験<span>2</span>、<span>2020</span>年<span>12</span>月<span>2</span>日に作成されたデータファイル

  * ファイル名：`20201202_HB_EXP2_HEL_DATA_V03.xls`
  * 説明：`Time_ProjectAbbreviation_ExperimentNumber_Location_TypeOfData_VersionNumber`
  
* Meg Megsonが<span>2020</span>年<span>12</span>月<span>3</span>日に撮影したアリの頭のトリミングされた画像

  * ファイル名：`20201203_MM_HEAD_CROPPED_V1.psd`
  * 説明：`Time_CreatorData_TypeModification_Version`

## **ファイルのバージョン管理はどのように行うのか？**

### **概要**

ファイルのバージョン管理は、ファイルやデータセットに加えられた変更を追跡するための方法です。適切なファイル命名規則を実装することで、異なるバージョンの存在を示すことができますが、それだけでは<span>2</span>つ（またはそれ以上）のバージョンの違いを説明することはできません。ファイルのバージョン管理は、どのアクションや変更がいつ行われたかを明らかにし、前のバージョンには存在していたが、後に削除されたり変更されたりしたものを、さかのぼって見つけることを容易にします。

### **考察**

* 同じタイミングで共同作業を行う必要がありますか？
* 前のバージョンに戻ったり、復元したりする必要がありますか？
* 多くの変更が行われますか？

### **ソリューション**

* バージョンの変更があまりない場合、例えば、各ファイルの変更点をバージョンごとに文書化したログを保管することで、手動で管理することができます。
* 自動でのバージョン管理、コンフリクトの解決、バックトレースの機能については、[<span>GitHub</span>](https://github.com/)や[<span>BitBucket</span>](https://bitbucket.org/)などでホストされている[<span>Git</span>](https://git-scm.com/)などの適切なバージョン管理ソフトウェアを使用します。
* ファイルの自動バージョン管理機能を備えたクラウドストレージサービス（[データストレージ](/storage)のページを参照）を利用します。スプレッドシート、テキストファイル、スライドなどには非常に便利です。

## **ファイルをフォルダ構造で整理するには？**

### **概要**

わかりやすいフォルダ名と直観的な設計になるよう、慎重に計画されたフォルダ構造は、良いデータ整理の基礎となります。フォルダ構造は、どの情報がどこにあるのかという概要を示し、現在のステークホルダーだけでなく、将来のステークホルダーもプロジェクトで作成されたファイルが理解できるようになります。

### **考察**

* ファイルをどのように整理するかの決定は、プロジェクトの計画・設計時に行い、最初から戦略的に実行できるようにします。
* 研究グループ内のすべてのプロジェクトで、同じ戦略を一貫して適用することを検討してください。

### **ソリューション**

フォルダは、以下の指針に沿う必要があります<span>:</span>

* プロジェクトの設計とワークフローに対応したフォルダとサブフォルダの構造を持つ。
* 必要な長さだけの分かりやすい名前をつける。
* 固有の名前をつける<span> - </span>フォルダとサブフォルダに同じ名前をつけないこと。

一番上のフォルダには、フォルダ構造とその中にどのようなファイルが含まれているかを説明した<span>README.txt</span>ファイルを置きます。このファイルには、ファイルの命名規則についての説明も含まれる必要があります。「[<span>A Quick Guide to Organizing Computational Biology Projects</span>](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1000424)」も参照しましょう。

**例<span>:</span>**

project/  
code/　　　　　　　　　code needed to go from input files to final results  
data/　　　　　　　　　 raw and primary data (never edit!)  
raw_external/  
raw_internal/  
meta/  
doc/　　　　　　　　　　documentation of the study  
intermediate/　　　　　　output files from intermediate analysis steps  
logs/　　　　　　　　　　logs from the different analysis steps  
notebooks/　　　　　　　notebooks that document your day-to-day work  
results/　　　　　　　　　output from workflows and analyses  
figures/  
reports/  
tables/  
scratch/　　　　　　　　　temporary files that can safely be deleted or lost  
README.txt 　　　　　　　file and folder description
