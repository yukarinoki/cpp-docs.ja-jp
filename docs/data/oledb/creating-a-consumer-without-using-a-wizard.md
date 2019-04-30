---
title: ウィザードを使用しないコンシューマーの作成
ms.date: 10/12/2018
helpviewer_keywords:
- OLE DB consumers, creating
ms.assetid: e8241cfe-5faf-48f8-9de3-241203de020b
ms.openlocfilehash: 029fe6866df81d366cc3bc15096f638791faa413
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362505"
---
# <a name="creating-a-consumer-without-using-a-wizard"></a>ウィザードを使用しないコンシューマーの作成

次の例では、既存の ATL プロジェクトに OLE DB コンシューマーのサポートを追加することを前提としています。 実行する必要があります、MFC アプリケーションに OLE DB コンシューマーのサポートを追加する場合、 **MFC アプリケーション ウィザード**がすべてのサポートを必要な作成され、アプリケーションを実行するために必要な MFC ルーチンを呼び出します。

使用せずに OLE DB コンシューマーのサポートを追加する、 **ATL OLE DB コンシューマー ウィザード**:

- Pch.h ファイルで、次を追加`#include`ステートメント。

    ```cpp
    #include <atlbase.h>
    #include <atldbcli.h>
    #include <atldbsch.h> // if you are using schema templates
    ```

プログラムでは、コンシューマーは、通常、次の一連の操作を実行します。

1. ローカル変数に列をバインドするユーザー レコード クラスを作成します。 この例で`CMyTableNameAccessor`ユーザー レコード クラスは、(を参照してください[ユーザー レコード](../../data/oledb/user-records.md))。 このクラスには、列のマップとパラメーターのマップが含まれています。 列マップで指定したフィールドごとにユーザー レコード クラスのデータ メンバーを宣言します。これらのデータ メンバーのそれぞれについてもに、ステータスのデータ メンバーと長さのデータ メンバーを宣言します。 詳細については、次を参照してください。[ウィザードで生成されたアクセサーのフィールド ステータス データ メンバー](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md)します。

    > [!NOTE]
    > 独自のコンシューマーを作成する場合、ステータスや長さ変数より前に、データ変数を引き起こすことがあります。

- データ ソースとセッションをインスタンス化します。 使用して、使用して、行セットのインスタンスを作成し、アクセサーと行セットの型を判断する[CCommand](../../data/oledb/ccommand-class.md)または[CTable](../../data/oledb/ctable-class.md):

    ```cpp
    CDataSource ds;
    CSession ss;
    class CMyTableName : public CCommand<CAccessor<CMyTableNameAccessor>>
    ```

- 呼び出す`CoInitialize`COM を初期化するには これは、メインのコードで呼び出されます。 例えば:

    ```cpp
    HRESULT hr = CoInitialize(NULL);
    ```

- 呼び出す[cdatasource::open](../../data/oledb/cdatasource-open.md)またはそのバリエーションの 1 つ。

- データ ソースへの接続を開き、セッションを開きとを開くと、行セットを初期化 (を場合、コマンドも実行します)。

    ```cpp
    hr = ds.Open();
    hr = ss.Open(ds);
    hr = rs.Open();            // (Open also executes the command)
    ```

- 必要に応じて、行セット プロパティの設定を使用して`CDBPropSet::AddProperty`へのパラメーターとして渡すと`rs.Open`します。 これを行う方法の例は、次を参照してください。`GetRowsetProperties`で[コンシューマー メソッド](../../data/oledb/consumer-wizard-generated-methods.md)します。

- データの取得/操作に行セットを使えるようになりました。

- アプリケーションが終了すると、接続、セッション、および行セットを閉じます。

    ```cpp
    rs.Close();
    ss.Close();
    ds.Close();
    ```

   コマンドを使用している場合を呼び出すことがある`ReleaseCommand`後`Close`します。 コード例で[ccommand::close](../../data/oledb/ccommand-close.md)を呼び出す方法を示しています`Close`と`ReleaseCommand`します。

- 呼び出す`CoUnInitialize`COM. の初期化を解除するには これは、メインのコードで呼び出されます。

    ```cpp
    CoUninitialize();
    ```

## <a name="see-also"></a>関連項目

[OLE DB コンシューマーの作成](../../data/oledb/creating-an-ole-db-consumer.md)