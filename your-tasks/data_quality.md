## **研究データの品質をどのように確保しているか？**

### **概要**

データ品質という言葉は、さまざまに理解することができます。企業の文脈では、多くの場合ISO 8000規格で定義されたマスターデータ管理を指しています。学術においては、データの品質は、ある特定の目的のためにデータを（再）利用する際の適合性と密接に関連しており、研究データの重要な属性です。データの品質は、研究結果の信頼性に影響を与え、二次研究におけるデータの再利用性を高める重要な要因となります。データの品質管理は、研究データのライフサイクルのどの段階でも行うことができます。そのため、データ管理の計画時に必要な手順を確実に定義しておく必要があります。

### **考察**

* データ収集の仕組みはどうなっているのでしょうか？品質管理は、データ収集時に行われるのが一般的です。データ収集の要素によって、実施可能な品質対策が決まります。対策の例は以下の通りです：

    * データ作成者、データ分析者、データ管理者を含むデータ管理ワーキンググループ（DMWG）を設置する。
    * データ収集時：データを収集する前に、データ辞書（検証ルールを含む）を定義する。
    * メタデータ収集時：メタデータのデータテンプレートを定義する。
    * 電子データ収集システムを使用する。
    * ツール、パイプライン、ダッシュボードによる自動品質モニタリングを行う。
    * 研究参加者、研究者、調査員、その他関係者のトレーニングを行う。
    * 分野の標準（standards）を採用する。
    * 機器の校正（キャリブレーション）を行う。
    * サンプリングを繰り返す。
    * 収集後のデータキュレーションを行う。
    * データのピアレビューを行う。

* あなたの研究分野では、品質に関する基準や確立された作業方法がありますか？臨床研究や次世代シーケンサーなどの特定の分野では、データの品質を確保するための一般的な作業方法があります。
* データ全体の品質を定義し評価するためのフレームワークは、以下のような文献で数多く提案されています：

    * [Wang](http://www.jstor.org/stable/40398176?origin=JSTOR-pdf)による<span>データ品質の４つの次元</span>（Accuracy (正確性)、Relevancy(関連性)、Representation(表現性)、Accessibility(アクセス性) ）
    * 電子医療データに対する、[Sherman](https://doi.org/10.1016/C2012-0-06937-2)による5つのC（ Clean(清潔)、Consistent(一貫)、Conformed(適合)、Current(最新)、Comprehensive(包括) ）と[Kahn](https://dx.doi.org/10.13063/2327-9214.1244)の3つのカテゴリー（ Conformance(適合性)、Completeness(完全性)、Plausibility(妥当性) ）。また、Kahnはこれらの構成要素を評価するために、2つの異なるモードを提案している：

        * 検証（verification：フォーマットや指定された値の範囲への準拠など、本質的な一貫性に焦点を当てる）。
        * 妥当性の確認（validation：外部ベンチマークに対する値の整合性に焦点を当てる）。

    * 医療データの場合、データ品質が何を意味するのかを理解する良い例が、[OHDSI](https://www.ohdsi.org/)コミュニティにあります。この場合の文脈は、[OMOP共通データモデル](https://ohdsi.github.io/CommonDataModel/)で表現される観察医療データです。

### **ソリューション**

* 電子データ収集システム：[REDCap](https://www.project-redcap.org/)では、電子データ収集フォームを設計することができ、それらのフォームを介して収集されたデータの品質を監視することができます。
* データ収集に必要な変数について、定義すべき要素や要因を示した[データ辞書の例](https://webdav-r3lab.uni.lu/public/elixir/templates/Data_dictionary_example.xlsx)があります。
* 世界銀行では、調査の設計と実施に関する[品質保証ガイダンス](https://dimewiki.worldbank.org/wiki/Data_Quality_Assurance_Plan)を提供しています。
* U.S. National Institute's of Health'sでは、データ品質に関する[入門的なトレーニング資料](https://oir.nih.gov/sites/default/files/uploads/sourcebook/documents/ethical_conduct/data_quality_management-2015_05_15.pdf)を提供しています。
* Bio.toolsでは、[ライフサイエンスにおけるデータ品質管理のための計算ツールとパイプライン](https://bio.tools/t?page=1&q=quality&sort=score)を紹介しています。
* [Pentaho Community Edition（CE）](https://www.hitachivantara.com/en-us/products/dataops-software/data-integration-analytics/pentaho-community-edition.html)や[Talend Open Studio](https://sourceforge.net/projects/talend-studio/)など、データ品質を監視・確認するための定義済みの構成要素を含むデータ統合ツールがあります。
* 品質問題の特定、修正・キュレーション、収集したデータの変換の実行を、使いやすいグラフィックインターフェースと視覚化で支援する[OpenRefine](https://openrefine.org/)などのデータキュレーションツールがあります。また、再現性とバックトラックのために、キュレーション中のすべてのステップを文書化します。
* 医療データの場合：

    * [The Book of OHDSI](http://book.ohdsi.org/)には、観察医療データセットのデータ品質を評価する方法について、データ品質、臨床の妥当性、ソフトウェアの妥当性、方法の妥当性ごとに分かれたいくつかの章があります。  
        [OHDSI Data Quality Dashboard](https://github.com/OHDSI/DataQualityDashboard)は、[OMOP共通データモデル](https://ohdsi.github.io/CommonDataModel/)で表現された、日常的に生成される健康データの品質と適合性を評価するためのソフトウェアフレームワークです。文献で提案されている全体的なデータの質を定義し評価するためのフレームワークは、上記のKahnフレームワークを活用した[OHDSI Data Quality Dashboard](https://github.com/OHDSI/DataQualityDashboard)のように、データセットの品質を可視化するために使用できます（オリジナルの[thehyve.nl blogpost](https://www.thehyve.nl/articles/fair-data-for-machine-learning)から改編）。