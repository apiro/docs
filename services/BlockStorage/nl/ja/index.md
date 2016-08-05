{:new_window: target="_blank"} 

# {{site.data.keyword.blockstorageshort}} (Beta) 入門

*最終更新日: 2016 年 7 月 15 日*
{: .last-updated}

{{site.data.keyword.blockstoragefull}} では、永続性ストレージを必要とするトランザクション集約型のワークロードやランタイムのために、ブロック・レベルのストレージにアクセスできます。

IBM {{site.data.keyword.blockstorageshort}} for {{site.data.keyword.Bluemix_notm}} を使用して、仮想サーバーに接続可能な {{site.data.keyword.blockstorageshort}} ボリュームを作成できます。ブロック・ストレージ・ボリュームに格納されたデータは、お使いの仮想サーバーのライフサイクルが過ぎても存続します。IBM {{site.data.keyword.blockstorageshort}} では、OpenStack Cinder を使用してボリュームのライフサイクルを管理します。

{{site.data.keyword.blockstorageshort}} ボリュームは、IBM {{site.data.keyword.blockstorageshort}} サービス・インスタンスを使用して作成します。このボリュームは、特定のデバイスの下で仮想サーバーに接続できます。そのデバイスはユーザーが指定しますが、使用可能なデバイス名をシステムが自動的に選択することもできます。仮想サーバーは入出力操作を、{{site.data.keyword.blockstorageshort}} サービスとは無関係に、指定のデバイスを使用して直接実行します。

ボリュームのスナップショットをブロック・レベルで作成することもできます。{{site.data.keyword.blockstorageshort}} サービスでは、ボリュームが接続中の場合は、そのボリュームのスナップショットを作成することは許可されません。したがって、作成されたスナップショットはクラッシュ対応になります。 


## {{site.data.keyword.blockstorageshort}} サービスのインスタンス作成方法
お使いのスペースで {{site.data.keyword.blockstorageshort}} サービスのインスタンスを作成するには、以下のステップに従います。
 
1.	{{site.data.keyword.Bluemix_notm}} の**「カタログ」**タブに移動して、検索ボックスに **{{site.data.keyword.blockstorageshort}}** と入力するか、**「サービス」**に移動して**「ストレージ」**を選択します。**{{site.data.keyword.blockstorageshort}}** サービスをクリックします。 
2.	スペース名とサービス名を入力します。プランを選択して、**「作成」**をクリックします。
 	
{{site.data.keyword.blockstorageshort}} サービスは、アンバインドされたコンテキストでのみサポートされます。 

ご使用のスペースに {{site.data.keyword.blockstorageshort}} サービスのインスタンスが作成されます。サービス・インスタンスのアイコンをクリックすれば、いつでも {{site.data.keyword.blockstorageshort}} UI を開いてボリュームを管理できます。



## {{site.data.keyword.blockstorageshort}} ユーザー・インターフェース (UI) の使用 {: #using-block-storage-ui}
{{site.data.keyword.blockstorageshort}} のグラフィカル・ユーザー・インターフェースでは、ウィンドウ上部に、ストレージ・ボリューム、スナップショット、およびボリュームとスナップショット双方の総ストレージ消費量の概要が表示されます。 

ヘッダーには、最後に UI が最新表示にされた日時が含まれています。必要なら「最新表示」アイコン (円と矢印のアイコン) をクリックして、UI を手動で最新表示にすることができます。 

入力したストリングに基づいてボリュームを探すには検索バーを使用します。入力すると、それにつれて表がフィルタリングされていき、入力した検索ストリングに一致するボリュームのみが表示されます。

概要の下には、ボリューム用とスナップショット用の 2 つのタブがあります。デフォルトでは、ボリュームのタブが選択されています。このタブに載っている表には、使用可能なボリュームと接続済みのボリュームに関する詳細な情報がリストされています。表内のそれぞれの行には、ボリュームの最も重要なプロパティーが表示されます。行を広げれば、より多くのプロパティーが表示されます。接続済みのボリュームには、そのボリュームの接続先の仮想サーバーのインスタンスとデバイスも表示されます。 

スナップショットのタブには、類似のプロパティーと動作を持つスナップショットの表が表示されます。 

新規ボリュームを作成したり、既存ボリュームを操作したりするには、表の上にある「作成」アイコンを使用します。スナップショットからボリュームを作成する場合は、「アクション」ドロップダウン・リストを使用することもできます。




## 仮想サーバーに対するボリュームの接続 {: #attaching-detaching-volume}
ボリュームは、具体的なデバイス名を持ったデバイスとして、仮想サーバーに接続されたり切り離されたりします。仮想サーバーがデータをボリューム上で永続的に保持できるようにするには、そのボリュームを仮想サーバーに接続する必要があります。

ボリュームを接続するには以下のステップに従います。 

1.	使用可能なボリュームのリストからボリュームを選択します。
2.	**「接続 (Attach)」**をクリックします。
3.	「接続 (Attach)」ダイアログで、ドロップダウン・リストから仮想サーバーのインスタンスを選択します。 
4.	オプションで、そのボリュームの接続に使用するデバイスを指定します。デバイスを指定しない場合は、仮想サーバーで使用可能なデバイスのうち最初のものがシステムによって自動的に選択されます。
5.	**「接続 (Attach)」**をクリックして情報を送信し、ダイアログを閉じます。

このボリュームは、仮想サーバーのインスタンスに関する情報と併せて、接続済みボリュームの表にリストされます。
これで、仮想サーバーがデバイスを使ってデータを永続的に保持できるようになりました。 


# 関連リンク
{: #rellinks}

## API リファレンス
{: #api}
* [OpenStack Block Storage (Cinder) API v2](http://developer.openstack.org/api-ref-blockstorage-v2.html){: new_window}
