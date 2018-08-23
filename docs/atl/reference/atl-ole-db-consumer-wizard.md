---
title: ATL OLE DB コンシューマー ウィザード |Microsoft Docs
ms.custom: ''
ms.date: 06/25/2018
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
ms.openlocfilehash: 2a03e29ed5197d27b421135b1561f3edc88af596
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42573333"
---
# <a name="atl-ole-db-consumer-wizard"></a>ATL OLE DB コンシューマー ウィザード
このウィザードを設定する OLE DB コンシューマー クラス、データ バインディングで指定された OLE DB プロバイダーを指定したデータ ソースにアクセスするために必要です。  
  
> [!NOTE]
>  このウィザードでは、をクリックする必要があります、**データソース**で名前を入力する前に、データ ソースを選択するボタン、`Class`と **.h ファイル**フィールド。  
  
## <a name="uielement-list"></a>UIElement の一覧  
**Data Source**  
**データソース**ボタンを指定した OLE DB プロバイダーを使用して、指定されたデータ ソースを設定することができます。 このボタンをクリックすると、**データ リンク プロパティ** ダイアログ ボックスが表示されます。 接続文字列の作成の詳細については、**データ リンク プロパティ**ダイアログ ボックスを参照してください[Data Link API の概要](/previous-versions/windows/desktop/ms718102\(v=vs.85\))Windows SDK のドキュメント。  
  
> [!NOTE]
>  Shift キーを押し、以前のリリースで、**データソース**Data Link (.udl) ファイルを選択できるようにファイルを開く ダイアログを開くボタンをクリックします。 この機能はサポートされなくなりました。  
  
ダイアログ ボックスでは、4 つのタブがあります。  
  
 - **プロバイダー**  タブ  
  
 - **接続** タブ  
  
 - **高度な** タブ  
  
 - **すべて** タブ  
  
次の追加情報がタブについて説明します、**データ リンク プロパティ** ダイアログ ボックス。  
  
をクリックして**OK**を完了します。 **データベース オブジェクトの選択** ダイアログ ボックスが表示されます。 このダイアログ ボックスからテーブル、ビュー、またはコンシューマーが使用するストアド プロシージャを選択します。  
  
 **Provider**  
   データ ソースへの接続を管理する適切なプロバイダーを選択します。 プロバイダーの種類は、通常、接続先データベースの種類によって決まります。 をクリックして、**次**ボタンまたはをクリックして、**接続**タブ。  
  
 **接続**  
   このタブの内容は、選択したプロバイダーによって異なります。 ここで、2 つの接続は、さまざまな種類のプロバイダーがありますが、最も一般的な: SQL および ODBC のデータ。 他のユーザーは、ここで説明するフィールドのようなバリエーションです。  
  
  SQL データ。  
  
   1. **選択するか、サーバー名を入力:** ネットワークに登録されているデータのすべてのサーバーを表示するドロップダウン メニューをクリックし、いずれかを選択します。  
  
   2. **サーバーにログオンする情報を入力します:** ユーザー名とデータ サーバーにログオンするためのパスワードを入力します。  
  
   3. **サーバー上のデータベースを選択します:** データ サーバーに登録されているすべてのデータベースを表示するドロップダウン メニューをクリックし、いずれかを選択します。  
  
         - または -  
  
    **データベース名としてのデータベース ファイルをアタッチ:** データベースとして使用するファイルの指定は、明示的なパス名を入力します。  
  
    > [!NOTE]
    >  データ リンク プロパティ ダイアログ ボックスの「パスワードを保存する」機能でセキュリティの問題があります。 「サーバーにログオンする入力は、」では、2 つのラジオ ボタンがあります。  
  
    **Windows NT 統合セキュリティを使用します。**  
  
    **特定のユーザー名とパスワードを使用します。**  
  
     選択した場合**特定のユーザー名とパスワードを使用して、**、(「パスワードの保存を許可する」のチェック ボックスを使用して) パスワードを保存するオプションがあります。 ただし、このオプションは安全ではありません。 選択することをお勧め**統合セキュリティを使用して Windows NT**; パスワードが暗号化されるため、このオプションはセキュリティで保護します。  
  
     「パスワードを保存する」を選択する状況もあります。 たとえば、プライベート データベース ソリューションのライブラリをリリースする場合する必要があります、データベースに直接アクセスできませんは代わりに使用中間層アプリケーション (選択した任意の認証方法) を介してユーザーを確認し、データの並べ替えを制限するにはユーザーが使用できます。  
  
     ODBC データ。  
  
     1. **データのソースを指定:** データ ソース名または接続文字列を使用することができます。  
  
    **データ ソース名を使用:** このドロップダウン リストには、コンピューターに登録されているデータ ソースが表示されます。 事前に、ODBC データ ソース アドミニストレーターを使用してデータ ソースを設定することができます- または -**接続文字列を使用:** 取得済み、またはをクリックする、接続文字列を入力するか、**ビルド**ボタンは、**データ ソースの選択** ダイアログ ボックスが表示されます。 ファイルまたはマシンのデータ ソースを選択し、クリックして**OK**します。  
  
     > [!NOTE]
     >  接続文字列を取得するには、サーバー エクスプ ローラーで既存の接続のプロパティを表示または接続を作成するにはダブルクリックして**接続の追加**サーバー エクスプ ローラー。  
  
     2. **サーバーにログオンする情報を入力します:** ユーザー名とデータ サーバーにログオンするためのパスワードを入力します。  
  
     3. 使用する初期カタログを入力します。  
  
     4. をクリックして**接続のテスト**、テストが成功したかどうかはクリックして**OK**。 ない場合は、ログオン情報を調べて、別のデータベースまたはデータの別のサーバーを実行してください。  
  
**詳細設定**  
  **ネットワークの設定:** を指定する、**偽装レベル**(サーバーがクライアントを偽装するときに使用できる; RPC 偽装レベルに直接対応している権限借用のレベル) と**保護レベル**(クライアントとサーバーの間のデータの保護のレベルで送信される RPC 保護レベルに直接対応)。  
  
  **その他:** で**接続のタイムアウト**タイムアウトが発生する前に許容されるアイドル時間の秒数を指定します。 **アクセス許可**、データ接続のアクセス許可を指定します。  
  
    For more information about advanced initialization properties, refer to the documentation provided with each specific OLE DB provider.  
  
**All**  
     このタブには、データ ソースと指定した接続の初期化プロパティの概要が表示されます。 これらの値を編集することができます。  
  
     Click **OK** to finish. The **Select Database Object** dialog box appears. From this dialog box, select the table, view, or stored procedure that the consumer will use.  
  
 `Class`  
 データ ソースを選択すると、このボックスには、テーブルまたは選択したストアド プロシージャに基づく既定のクラス名が設定されます (を参照してください**データ ソースの選択**以下)。 クラス名を編集することができます。  
  
 **.h ファイル**  
 データ ソースを選択すると、このボックスには、テーブルまたは選択したストアド プロシージャに基づく既定のヘッダー クラス名が設定されます (を参照してください**データ ソースの選択**以下)。 ヘッダー ファイルの名前を編集したり、既存のヘッダー ファイルを選択することができます。  
  
 **属性付き**  
 このオプションは、ウィザードが属性またはテンプレート宣言を使用してコンシューマー クラスを作成するかどうかを指定します。 このオプションを選択すると、ウィザードは、テンプレートの宣言 (これは、既定のオプションです) ではなく属性を使用します。 このオプションをオフにすると、ウィザードは、属性ではなくテンプレート宣言を使用します。  
  
 -   コンシューマーを選択した場合**型**ウィザードを使用して、テーブルの`db_source`と`db_table`クラス宣言では、テーブルとテーブルのアクセサーを作成する属性を使用して`db_column`など、列マップを作成します。  
  
```
 // Inject table class and table accessor class declarations  
 [db_source("<initialization_string>"), db_table("dbo.Orders")]  
 ... 
 // Column map  
 [ db_column(1, status=m_dwOrderIDStatus, length=m_dwOrderIDLength) ] LONG m_OrderID;  
 [ db_column(2, status=m_dwCustomerIDStatus, length=m_dwCustomerIDLength) ] TCHAR m_CustomerID[6];  
 ...
```
  
   使用する代わりに、`CTable`テーブルとテーブル アクセサー クラスでは、たとえば、列マップを作成する BEGIN_COLUMN_MAP と END_COLUMN_MAP マクロを宣言するテンプレート クラス。  
  
``` 
 // Table accessor class  
    class COrdersAccessor; // Table class  
    class COrders : public CTable<CAccessor<COrdersAccessor>>;  
 ... 
 // Column map  
    BEGIN_COLUMN_MAP(COrderDetailsAccessor) 
    COLUMN_ENTRY_LENGTH_STATUS(1, m_OrderID, m_dwOrderIDLength, m_dwOrderIDStatus)  
    COLUMN_ENTRY_LENGTH_STATUS(2, m_CustomerID, m_dwCustomerIDLength, m_dwCustomerIDStatus)  
 ...  
    END_COLUMN_MAP() 
```  
  
-   コンシューマーを選択した場合**型**コマンドのウィザードを使用して、`db_source`と`db_command`属性、および使用`db_column`など、列マップを作成します。  
  
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
 これらのコンシューマー クラスをから派生するかどうかを指定するラジオ ボタンのいずれかを選択`CTable`または`CCommand`(既定値)。  
  
 **テーブル**  
 使用する場合は、このオプションを選択`CTable`または`db_table`クラス宣言にテーブルとテーブルのアクセサーを作成します。  
  
 **コマンド**  
 使用する場合は、このオプションを選択`CCommand`または`db_command`クラス宣言に、コマンドとコマンドのアクセサーを作成します。 これは、既定の選択です。  
  
 **サポート**  
 (既定値は none です)、コンシューマーでサポートされる更新プログラムの種類を指定するチェック ボックスを選択します。 次の各設定は[DBPROP_IRowsetChange](/previous-versions/windows/desktop/ms715892\(v=vs.85\))の適切なエントリ[DBPROP_UPDATABILITY](/previous-versions/windows/desktop/ms722676\(v=vs.85\))プロパティにマップを設定します。  
  
 **変更**  
 コンシューマーが行セットの行のデータの更新をサポートするを指定します。  
  
 **[挿入]**  
 コンシューマーが行セットに行の挿入をサポートするを指定します。  
  
 **削除**  
 コンシューマーが行セットから行の削除をサポートするを指定します。  
  
## <a name="see-also"></a>関連項目  
 [ATL OLE DB コンシューマー](../../atl/reference/adding-an-atl-ole-db-consumer.md)   
 [コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [接続文字列およびデータ リンク (OLE DB)](/previous-versions/windows/desktop/ms718376\(v=vs.85\))
