---
title: 'データ ソース: 接続 (ODBC) の管理 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC data sources [C++], multiuser environments
- generalizing connection strings
- ODBC [C++], disconnecting from data sources
- connection strings [C++], generalizing
- database connections [C++], creating
- GetDefaultConnect method
- connections [C++], data source
- ODBC connections [C++], configuring
- disconnecting from data sources
- databases [C++], connecting to
- ODBC connections [C++], disconnecting
- data sources [C++], connecting to
- ODBC connections [C++], connecting to data source
- ODBC data sources [C++], connections
- database connections [C++], MFC ODBC classes
ms.assetid: c0adbcdd-c000-40c6-b199-09ffdc7b6ef2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 100c06773a8f0ffa79631339384bd4ec42fa4b52
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33091830"
---
# <a name="data-source-managing-connections-odbc"></a>データ ソース : 接続 (ODBC)
このトピックの内容は、MFC ODBC クラスに該当します。  
  
 このトピックでは、次の内容について説明します。  
  
-   [データ ソースを構成する方法](#_core_configuring_a_data_source)です。  
  
-   [データ ソースと、レコード セットのマルチ ユーザー環境のしくみ](#_core_working_in_a_multiuser_environment)です。  
  
-   [データ ソースへの接続文字列の汎用](#_core_generalizing_the_connection_string)です。  
  
-   [データ ソースに接続する方法](#_core_connecting_to_a_specific_data_source)です。  
  
-   [データ ソースから切断する方法](#_core_disconnecting_from_a_data_source)です。  
  
-   [CDatabase オブジェクトを再利用する方法](#_core_reusing_a_cdatabase_object)です。  
  
 データ ソースとの接続とは、データにアクセスするために DBMS との通信を確立することです。 ODBC ドライバーを通じてデータ ソースと接続すると、データ ソースの位置がローカルでもネットワークでも、自動的に接続されます。  
  
 ODBC ドライバーがあるデータ ソースならば、どのデータ ソースにでも接続できます。 アプリケーションのユーザーも、同じ ODBC ドライバーを持つ必要があります。 ODBC ドライバーの再配布の詳細については、次を参照してください。 [ODBC の構成要素を、顧客に](../../data/odbc/redistributing-odbc-components-to-your-customers.md)です。  
  
##  <a name="_core_configuring_a_data_source"></a> データ ソースを構成します。  
 データ ソースの設定は、ODBC データ ソース アドミニストレーターを使って行います。 データ ソースの追加や削除も行うことができます。 アプリケーションを作成する際には、ODBC データ ソース アドミニストレーターを使用してデータ ソースを追加するようにアプリケーションのユーザーに指示するか、アプリケーション内で ODBC インストール呼び出しを直接行って ODBC データ ソース アドミニストレーターの機能を組み込むことができます。 詳細については、次を参照してください。 [ODBC アドミニストレーター](../../data/odbc/odbc-administrator.md)です。  
  
 データ ソースとして、Excel ファイルを使用してが登録されに表示されるように、ファイルを構成する必要があります、**データ ソースの選択** ダイアログ ボックス。  
  
#### <a name="to-use-an-excel-file-as-a-data-source"></a>Excel のファイルをデータ ソースとして使うには  
  
1.  ODBC データ ソース アドミニストレーターを使ってファイルを設定します。  
  
2.  **ファイル DSN**  タブで、をクリックして**追加**です。  
  
3.  **データ ソースの新規作成** ダイアログ ボックスは、Excel ドライバーを選択し、をクリックして**次**です。  
  
4.  をクリックして**参照**、データ ソースとして使用するファイルの名前を選択します。  
  
> [!NOTE]
>  選択する必要があります**すべてのファイル**.xls ファイルを表示するドロップダウン メニューにします。  
  
1.  **[次へ]** をクリックし、 **[完了]** をクリックします。  
  
2.  **ODBC Microsoft Excel Setup**  ダイアログ ボックスで、データベースのバージョンとブックを選択します。  
  
##  <a name="_core_working_in_a_multiuser_environment"></a> マルチ ユーザー環境での操作  
 複数のユーザーが同じデータ ソースにアクセスする場合は、自分がアクセスしているレコードセットのデータが、ほかのユーザーによって変更されてしまうおそれがあります。 同じように、自分が他のユーザーのレコードセットを変更してしまう場合もあります。 詳細については、次を参照してください。[レコード セット: レコード更新のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)と[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)です。  
  
##  <a name="_core_generalizing_the_connection_string"></a> 接続文字列を汎用化します。  
 ウィザードは、既定の接続文字列を使ってデータ ソースとの接続を行います。 アプリケーションの開発時には、この接続を使ってテーブルや列を表示できます。 しかし、この既定の接続文字列は、アプリケーションのユーザーがデータ ソースに接続する際に適切ではない場合もあります。 たとえば、実際に使われるデータ ソースおよびその位置を表すパスは、開発時とは異なる場合があります。 その場合は、する再実装する必要があります、 [:getdefaultconnect](../../mfc/reference/crecordset-class.md#getdefaultconnect)メンバーより汎用的なやり方で機能し、ウィザード実装を破棄します。 たとえば、次のような方法があります。  
  
-   ODBC データ ソース アドミニストレーターを使って接続文字列の登録、管理を行います。  
  
-   接続文字列を編集し、データ ソース名を削除します。 フレームワークによって、データ ソース名として ODBC が指定され、実行時には、ODBC では、データ ソース名などの必要な接続情報の入力を求めるダイアログ ボックスが表示されます。  
  
-   データ ソース名だけを指定します。 ODBC は、必要に応じて、ユーザー ID とパスワードの入力を求めます。 たとえば、元の接続文字列が次のようになっているとします。  
  
    ```  
    CString CApp1Set::GetDefaultConnect()  
    {  
       return "ODBC;DSN=afx;Trusted_Connection=Yes;";  
    }  
    ```  
  
     この接続文字列では、Windows NT 統合セキュリティを使用する、信頼関係接続を指定します。 セキュリティ上の重大な弱点が生成されるため、パスワードのハードコーディングや空白のパスワードの指定は避けてください。 その代わりに、`GetDefaultConnect` に新しい接続文字列を指定して、ユーザー ID とパスワードの問い合わせができます。  
  
    ```  
    // User must select data source and supply user ID and password:  
        return "ODBC;";  
    // User ID and password required:  
        return "ODBC;DSN=mydb;";  
    // Password required (myuserid must be replaced with a valid user ID):  
        return "ODBC;DSN=mydb;UID=myuserid;";  
    // Hard-coded user ID and password (SECURITY WEAKNESS--AVOID):  
        return "ODBC;DSN=mydb;UID=sa;PWD=777;";  
    ```  
  
##  <a name="_core_connecting_to_a_specific_data_source"></a> 特定のデータ ソースへの接続  
 特定のデータ ソースに接続する場合、データ ソース必要があります既にで構成されている[ODBC アドミニストレーター](../../data/odbc/odbc-administrator.md)です。  
  
#### <a name="to-connect-to-a-specific-data-source"></a>データ ソースに接続するには  
  
1.  `CDatabase` オブジェクトを構築します。  
  
2.  呼び出す、`OpenEx`または**開く**メンバー関数。  
  
 ウィザードを使用して指定されている以外のものである場合は、データ ソースを指定する方法の詳細については、次を参照してください[cdatabase::openex](../../mfc/reference/cdatabase-class.md#openex)または[cdatabase::open](../../mfc/reference/cdatabase-class.md#open)で、 *MFC。参照*です。  
  
##  <a name="_core_disconnecting_from_a_data_source"></a> データ ソースからの切断  
 呼び出しの前に開いているレコード セットをすべて閉じる必要があります、**閉じる**のメンバー関数`CDatabase`です。 関連付けられているレコード セットで、`CDatabase`オブジェクトを閉じると、保留中のいずれかに`AddNew`または**編集**ステートメントはキャンセルされ、すべて保留中のトランザクションはロールバックされます。  
  
#### <a name="to-disconnect-from-a-data-source"></a>データ ソースとの接続を終了するには  
  
1.  呼び出す、`CDatabase`オブジェクトの[閉じる](../../mfc/reference/cdatabase-class.md#close)メンバー関数。  
  
2.  再利用しない場合にはオブジェクトを破棄します。  
  
##  <a name="_core_reusing_a_cdatabase_object"></a> CDatabase オブジェクトを再利用  
 接続を終了した後で `CDatabase`オブジェクトを再利用できます。再利用時の接続先は、同じデータ ソースでも別のデータ ソースでもかまいません。  
  
#### <a name="to-reuse-a-cdatabase-object"></a>CDatabase オブジェクトを再利用するには  
  
1.  オブジェクトの元の接続を閉じます。  
  
2.  オブジェクトを破棄せずに呼び出すその`OpenEx`または**開く**メンバー関数は、もう一度です。  
  
## <a name="see-also"></a>関連項目  
 [データ ソース (ODBC)](../../data/odbc/data-source-odbc.md)   
 [データ ソース: データ ソース (ODBC) のスキーマを決定します。](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)   
 [CRecordset クラス](../../mfc/reference/crecordset-class.md)