---
title: ATL OLE DB コンシューマー ウィザード |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.consumer.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding ATL OLE DB consumers
- connection strings [C++], OLE DB consumers
- ATL OLE DB Consumer Wizard
ms.assetid: dcb68ed1-2224-422f-9f7b-108a74864204
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0d51569eaece5e3fac59c7cc2ff82a8454a5f959
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364951"
---
# <a name="atl-ole-db-consumer-wizard"></a>ATL OLE DB コンシューマー ウィザード
このウィザードを設定、OLE DB コンシューマー クラス、データ バインディングで、指定した OLE DB プロバイダーを介して指定されたデータ ソースにアクセスするために必要です。  
  
> [!NOTE]
>  このウィザードでは、をクリックする必要があります、**データソース**で名前を入力する前に、データ ソースを選択するにはボタン、`Class`と **.h ファイル**フィールドです。  
  
## <a name="uielement-list"></a>UIElement の一覧  
 **データ ソース**  
 **データソース**OLE DB プロバイダーを指定して、指定されたデータ ソースを設定することができます ボタンをクリックします。 このボタンをクリックすると、**データ リンク プロパティ** ダイアログ ボックスが表示されます。 接続文字列の作成の詳細については、**データ リンク プロパティ**ダイアログ ボックスを参照してください[データ リンク API の概要](https://msdn.microsoft.com/library/ms718102.aspx)Windows SDK のドキュメントです。  
  
> [!NOTE]
>  Shift キーをクリックすると、以前のリリースで、**データソース**ボタンは、データ リンク (.udl) ファイルを選択できるようにファイルを開く ダイアログを開きます。 この機能は現在サポートされていません。  
  
 ダイアログ ボックスには、4 つのタブがあります。  
  
- **プロバイダー**  タブ  
  
- **接続** タブ  
  
- **高度な** タブ  
  
- **すべて** タブ  
  
     次の追加情報が内のタブについて説明します、**データ リンク プロパティ** ダイアログ ボックス。  
  
     をクリックして**OK**を完了します。 **データベース オブジェクトの選択** ダイアログ ボックスが表示されます。 このダイアログ ボックスから、テーブル、ビュー、またはコンシューマーが使用するストアド プロシージャを選択します。  
  
 **プロバイダー**  
     データ ソースへの接続を管理するための適切なプロバイダーを選択します。 プロバイダーの種類は通常、接続先データベースの種類によって決まります。 クリックして、`Next`ボタンまたはをクリックして、**接続**タブです。  
  
 **接続**  
     このタブの内容は、選択したプロバイダーによって異なります。 ここで、2 つの接続は、さまざまな種類のプロバイダーがありますが、最も一般的な: SQL と ODBC のデータ。 その他は、ここで説明するフィールドのようなバリエーションです。  
  
     SQL データ。  
  
    1. **選択するか、サーバー名を入力:** ネットワーク上で登録済みのデータのすべてのサーバーを表示するドロップダウン リスト メニューをクリックし、いずれかを選択します。  
  
    2. **サーバーにログオンする情報を入力:** ユーザー名とデータ サーバーにログオンするためのパスワードを入力します。  
  
    3. **サーバー上のデータベースを選択:** データ サーバーに登録されているすべてのデータベースを表示するドロップダウン メニューをクリックし、いずれかを選択します。  
  
         - または -  
  
 **データベース名としてのデータベース ファイルをアタッチ:** データベースとして使用するファイルを指定以外の場合は、明示的なパス名を入力します。  
  
        > [!NOTE]
        >  There is a security problem with the "Allow saving of password" feature of the Data Link Properties dialog box. In "Enter information to log on to the server," there are two radio buttons:  
  
 **Windows NT 統合セキュリティを使用します。**  
  
 **特定のユーザー名とパスワードを使用します。**  
  
         If you select **Use a specific user name and password**, you have the option of saving the password (using the check box for "Allow saving password"); however, this option is not secure. It is recommended that you select **Use Windows NT integrated security**; this option is secure because it encrypts the password.  
  
         There might be situations in which you want to select "Allow saving password." For example, if you are releasing a library with a private database solution, you should not access the database directly but instead use a middle-tier application to verify the user (through whatever authentication scheme you choose) and then limit the sort of data available to the user.  
  
         For ODBC data:  
  
         1. **Specify the source of data:** You can use a data source name or a connection string.  
  
 **データ ソース名を使用:** このドロップダウン リストには、コンピューター上で登録されているデータ ソースが表示されます。 ODBC データ ソース アドミニストレーターを使用して前もってデータ ソースを設定することができます- または -**接続文字列を使用:** 既に取得しているかをクリックして、接続文字列を入力するか、**ビルド**ボタンをクリックします、。**データ ソースの選択** ダイアログ ボックスが表示されます。 ファイルまたはマシンのデータ ソースを選択し、クリックして**OK**です。  
  
        > [!NOTE]
        >  You can obtain a connection string by viewing the properties of an existing connection in Server Explorer, or you can create a connection by double-clicking **Add Connection** in Server Explorer.  
  
         2. **Enter information to log on to the server:** Enter a user name and password to log on to the data server.  
  
         3. Enter the initial catalog to use.  
  
         4. Click **Test Connection**; if the test succeeds, click **OK**. If not, check your logon information, try another database, or try another data server.  
  
 **詳細設定**  
 **ネットワークの設定:** を指定して、**偽装レベル**(、権限借用レベルをサーバーがクライアントを偽装するときに使用できる; RPC 偽装レベルに直接対応しています) と**保護レベル**(クライアントとサーバーの間でデータの保護のレベルが送信される RPC 保護レベルに直接対応)。  
  
 **その他:** で**接続のタイムアウト**タイムアウトが発生するまでのアイドル時間の秒数を指定します。 **アクセス許可**、データ接続のアクセス許可を指定します。  
  
     高度な初期化プロパティの詳細については、各 OLE DB プロバイダーに付属のマニュアルを参照してください。  
  
 **All**  
     このタブには、データ ソースと指定した接続の初期化プロパティの概要が表示されます。 これらの値を編集することができます。  
  
     をクリックして**OK**を完了します。 **データベース オブジェクトの選択** ダイアログ ボックスが表示されます。 このダイアログ ボックスから、テーブル、ビュー、またはコンシューマーが使用するストアド プロシージャを選択します。  
  
 `Class`  
 データ ソースを選択すると、このボックスには、テーブルまたは選択したストアド プロシージャに基づく既定のクラス名が設定されます (を参照してください**データ ソースの選択**下)。 クラス名を編集することができます。  
  
 **.h ファイル**  
 データ ソースを選択すると、このボックスには、テーブルまたは選択したストアド プロシージャに基づく既定のヘッダー クラス名が設定されます (を参照してください**データ ソースの選択**下)。 ヘッダー ファイルの名前を編集したり、既存のヘッダー ファイルを選択することができます。  
  
 **属性付き**  
 このオプションは、属性またはテンプレートの宣言を使用してコンシューマー クラスを作成するかどうかを指定します。 このオプションを選択すると、ウィザードは、テンプレートの宣言 (これは、既定のオプションです) ではなく属性を使用します。 このオプションの選択を解除するときに、ウィザードは、属性ではなくテンプレート宣言を使用します。  
  
-   コンシューマーを選択した場合**型**ウィザードを使用して、テーブルの`db_source`と**db_table**クラス宣言では、テーブルとテーブルのアクセサーを作成する属性を使用して**db_column**たとえば列マップを作成します。  
  
 ``` 
 // Inject table class and table accessor class declarations  
 [db_source("<initialization_string>"), db_table("dbo.Orders")]  
 ... 
 // Column map  
 [ db_column(1, status=m_dwOrderIDStatus, length=m_dwOrderIDLength) ] LONG m_OrderID;  
 [ db_column(2, status=m_dwCustomerIDStatus, length=m_dwCustomerIDLength) ] TCHAR m_CustomerID[6];  
 ...  
 ```  
  
     使用する代わりに、`CTable`テンプレート クラスは、テーブルとテーブル アクセサー クラスとマップを作成する、列、たとえば BEGIN_COLUMN_MAP および END_COLUMN_MAP マクロを宣言します。  
  
 ``` 
 // Table accessor class  
    class COrdersAccessor; *// Table class  
    class COrders : public CTable<CAccessor<COrdersAccessor>>;  
 ... 
 // Column map  
    BEGIN_COLUMN_MAP(COrderDetailsAccessor) 
    COLUMN_ENTRY_LENGTH_STATUS(1, m_OrderID, m_dwOrderIDLength, m_dwOrderIDStatus)  
    COLUMN_ENTRY_LENGTH_STATUS(2, m_CustomerID, m_dwCustomerIDLength, m_dwCustomerIDStatus)  
 ...  
    END_COLUMN_MAP() 
 ```  
  
-   コンシューマーを選択した場合**型**コマンド、ウィザードを使用して、`db_source`と**db_command** 、その属性を使用して**db_column**たとえば列マップを作成するには:  
  
 ```  
 [db_source("<initialization_string>"), db_command("SQL_command")]  
 ... 
 // Column map using db_column is the same as for consumer type of 'table'  
 ```  
  
     コマンドとコマンドのアクセサーを使用する代わりに、コマンド クラスの .h ファイル内の宣言をたとえばクラスします。  
  
 ```  
    Command accessor class:  
    class CListOrdersAccessor;  
    Command class:  
    class CListOrders : public CCommand<CAccessor<CListOrdersAccessor>>;  
 ... 
 // Column map using BEGIN_COLUMN_MAP ... END_COLUMN_MAP is the same as
 // for consumer type of 'table'  
 ```  
  
 参照してください[属性の基本的なしくみ](../../windows/basic-mechanics-of-attributes.md)詳細についてはします。  
  
 **Type**  
 コンシューマー クラスをから派生するかどうかを指定するには、このオプション ボタンのいずれかを選択`CTable`または`CCommand`(既定値)。  
  
 **テーブル**  
 使用する場合は、このオプションを選択`CTable`または**db_table**をクラス宣言にテーブルとテーブルのアクセサーを作成します。  
  
 **コマンド**  
 使用する場合は、このオプションを選択`CCommand`または**db_command**クラス宣言にコマンドとコマンドのアクセサーを作成します。 これは、既定の選択です。  
  
 **サポート**  
 (既定値は none です)、コンシューマーでサポートされる更新プログラムの種類を指定する チェック ボックスを選択します。 次の各設定は[DBPROP_IRowsetChange](https://msdn.microsoft.com/library/ms715892.aspx)の適切なエントリ[DBPROP_UPDATABILITY](https://msdn.microsoft.com/library/ms722676.aspx)プロパティ セット内にマップします。  
  
 **変更**  
 コンシューマーが行セットの行のデータの更新をサポートするを指定します。  
  
 **[挿入]**  
 コンシューマーが行セットに行の挿入をサポートするように指定します。  
  
 **削除**  
 コンシューマーが行セットから行の削除をサポートするように指定します。  
  
## <a name="see-also"></a>関連項目  
 [ATL OLE DB コンシューマー](../../atl/reference/adding-an-atl-ole-db-consumer.md)   
 [コード ウィザードによる機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [接続文字列およびデータ リンク (OLE DB)](https://msdn.microsoft.com/library/ms718376.aspx)
