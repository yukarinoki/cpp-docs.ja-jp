---
title: 'データ ソース : 接続 (ODBC)'
ms.date: 11/04/2016
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
ms.openlocfilehash: 107a5e20b70f67be74b6e6f861bd539446e9d4ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374529"
---
# <a name="data-source-managing-connections-odbc"></a>データ ソース : 接続 (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

このトピックでは、次の内容について説明します。

- [データ ソースを構成する方法](#_core_configuring_a_data_source):

- [マルチユーザー環境がデータ ソースとそのレコードセットに与える影響](#_core_working_in_a_multiuser_environment):

- [接続文字列をデータ ソースに一般化する理由](#_core_generalizing_the_connection_string)

- [データ ソースに接続する方法](#_core_connecting_to_a_specific_data_source)。

- [データ ソースから切断する方法](#_core_disconnecting_from_a_data_source)。

- [CDatabase オブジェクトを再利用する方法](#_core_reusing_a_cdatabase_object)。

データ ソースとの接続とは、データにアクセスするために DBMS との通信を確立することです。 ODBC ドライバーを通じてデータ ソースと接続すると、データ ソースの位置がローカルでもネットワークでも、自動的に接続されます。

ODBC ドライバーがあるデータ ソースならば、どのデータ ソースにでも接続できます。 アプリケーションのユーザーも、同じ ODBC ドライバーを持つ必要があります。 ODBC ドライバの再配布の詳細については[、「ODBC コンポーネントを顧客に再配布する](../../data/odbc/redistributing-odbc-components-to-your-customers.md)」を参照してください。

## <a name="configuring-a-data-source"></a><a name="_core_configuring_a_data_source"></a>データ ソースの構成

データ ソースの設定は、ODBC データ ソース アドミニストレーターを使って行います。 データ ソースの追加や削除も行うことができます。 アプリケーションを作成する際には、ODBC データ ソース アドミニストレーターを使用してデータ ソースを追加するようにアプリケーションのユーザーに指示するか、アプリケーション内で ODBC インストール呼び出しを直接行って ODBC データ ソース アドミニストレーターの機能を組み込むことができます。 詳細については[、「ODBC アドミニストレーター](../../data/odbc/odbc-administrator.md)」を参照してください。

Excel ファイルをデータ ソースとして使用でき、ファイルが登録され、[**データ ソースの選択**] ダイアログ ボックスに表示されるようにファイルを構成する必要があります。

#### <a name="to-use-an-excel-file-as-a-data-source"></a>Excel のファイルをデータ ソースとして使うには

1. ODBC データ ソース アドミニストレーターを使ってファイルを設定します。

1. [**ファイル DSN]** タブで [**追加**] をクリックします。

1. [**新しいデータ ソースの作成**] ダイアログ ボックスで、Excel ドライバを選択し、[**次へ**] をクリックします。

1. [**参照 ]** をクリックし、日付ソースとして使用するファイルの名前を選択します。

> [!NOTE]
> .xls ファイルを表示するには、ドロップダウン メニューの **[すべてのファイル**] を選択する必要がある場合があります。

1. **[次へ]** をクリックし、**[完了]** をクリックします。

1. ODBC **Excel セットアップ**ダイアログ ボックスで、データベースのバージョンとブックを選択します。

## <a name="working-in-a-multiuser-environment"></a><a name="_core_working_in_a_multiuser_environment"></a>マルチユーザー環境での作業

複数のユーザーが同じデータ ソースにアクセスする場合は、自分がアクセスしているレコードセットのデータが、ほかのユーザーによって変更されてしまうおそれがあります。 同じように、自分が他のユーザーのレコードセットを変更してしまう場合もあります。 詳細については、「[レコードセット : レコードセットがレコードを更新する方法 (ODBC)」](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)および「[トランザクション (ODBC)」](../../data/odbc/transaction-odbc.md)を参照してください。

## <a name="generalizing-the-connection-string"></a><a name="_core_generalizing_the_connection_string"></a>接続文字列の一般化

ウィザードは、既定の接続文字列を使ってデータ ソースとの接続を行います。 アプリケーションの開発時には、この接続を使ってテーブルや列を表示できます。 しかし、この既定の接続文字列は、アプリケーションのユーザーがデータ ソースに接続する際に適切ではない場合もあります。 たとえば、実際に使われるデータ ソースおよびその位置を表すパスは、開発時とは異なる場合があります。 その場合は[、CRecordset::GetDefaultConnect](../../mfc/reference/crecordset-class.md#getdefaultconnect)メンバー関数をより汎用的な方法で再実装し、ウィザードの実装を破棄する必要があります。 たとえば、次のような方法があります。

- ODBC データ ソース アドミニストレーターを使って接続文字列の登録、管理を行います。

- 接続文字列を編集し、データ ソース名を削除します。 フレームワークによって、データ ソース名として ODBC が指定され、実行時には、ODBC では、データ ソース名などの必要な接続情報の入力を求めるダイアログ ボックスが表示されます。

- データ ソース名だけを指定します。 ODBC は、必要に応じて、ユーザー ID とパスワードの入力を求めます。 たとえば、元の接続文字列が次のようになっているとします。

    ```cpp
    CString CApp1Set::GetDefaultConnect()
    {
       return "ODBC;DSN=afx;Trusted_Connection=Yes;";
    }
    ```

   この接続文字列は、Windows NT 統合セキュリティを使用する、信頼できる接続を指定します。 セキュリティ上の重大な弱点が生成されるため、パスワードのハードコーディングや空白のパスワードの指定は避けてください。 その代わりに、`GetDefaultConnect` に新しい接続文字列を指定して、ユーザー ID とパスワードの問い合わせができます。

    ```cpp
    // User must select data source and supply user ID and password:
        return "ODBC;";
    // User ID and password required:
        return "ODBC;DSN=mydb;";
    // Password required (myuserid must be replaced with a valid user ID):
        return "ODBC;DSN=mydb;UID=myuserid;";
    // Hard-coded user ID and password (SECURITY WEAKNESS--AVOID):
        return "ODBC;DSN=mydb;UID=sa;PWD=777;";
    ```

## <a name="connecting-to-a-specific-data-source"></a><a name="_core_connecting_to_a_specific_data_source"></a>特定のデータ ソースへの接続

特定のデータ ソースに接続するには、データ ソースが既に[ODBC アドミニストレータ](../../data/odbc/odbc-administrator.md)で構成されている必要があります。

#### <a name="to-connect-to-a-specific-data-source"></a>データ ソースに接続するには

1. `CDatabase` オブジェクトを構築します。

1. または`Open`メンバー`OpenEx`関数を呼び出します。

ウィザードで指定したデータ ソース以外のデータ ソースを指定する方法の詳細については *、MFC リファレンス*の[CDatabase::OpenEx](../../mfc/reference/cdatabase-class.md#openex)または[CDatabase::Open](../../mfc/reference/cdatabase-class.md#open)を参照してください。

## <a name="disconnecting-from-a-data-source"></a><a name="_core_disconnecting_from_a_data_source"></a>データ ソースからの切断

のメンバー関数を呼び出す前に`Close`、開いている`CDatabase`レコードセットをすべて閉じる必要があります。 閉じるオブジェクトに`CDatabase`関連付けられたレコードセットでは、保留中`AddNew`のステートメントや`Edit`ステートメントは取り消され、保留中のすべてのトランザクションがロールバックされます。

#### <a name="to-disconnect-from-a-data-source"></a>データ ソースとの接続を終了するには

1. オブジェクトの`CDatabase` [Close](../../mfc/reference/cdatabase-class.md#close)メンバー関数を呼び出します。

1. 再利用しない場合にはオブジェクトを破棄します。

## <a name="reusing-a-cdatabase-object"></a><a name="_core_reusing_a_cdatabase_object"></a>CDatabase オブジェクトの再利用

接続を終了した後で `CDatabase`オブジェクトを再利用できます。再利用時の接続先は、同じデータ ソースでも別のデータ ソースでもかまいません。

#### <a name="to-reuse-a-cdatabase-object"></a>CDatabase オブジェクトを再利用するには

1. オブジェクトの元の接続を閉じます。

1. オブジェクトを破棄する代わりに、そのオブジェクト`OpenEx`または`Open`メンバー関数を再度呼び出します。

## <a name="see-also"></a>関連項目

[データ ソース (ODBC)](../../data/odbc/data-source-odbc.md)<br/>
[データ ソース: データ ソースのスキーマの判定 (ODBC)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)<br/>
[クラス](../../mfc/reference/crecordset-class.md)
