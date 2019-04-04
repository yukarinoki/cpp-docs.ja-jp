---
title: 'レコードセット: 定義済みクエリを利用したクラスの宣言 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets, queries
- predefined queries and recordsets
- stored procedures, and recordsets
- recordsets, predefined queries
- recordsets, stored procedures
ms.assetid: d27c4df9-dad2-4484-ba72-92ab0c8ff928
ms.openlocfilehash: e83bf2ecb24a9abfd8dc9800a3a10d2d65025336
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611264"
---
# <a name="recordset-declaring-a-class-for-a-predefined-query-odbc"></a>レコードセット: 定義済みクエリを利用したクラスの宣言 (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

このトピックでは、定義済みクエリ (Microsoft SQL Server のように、ストアド プロシージャとも呼ばれます) のレコード セット クラスを作成する方法について説明します。

> [!NOTE]
>  このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。 バルク行フェッチを実装すると、プロセスはよく似ています。 バルク行フェッチを実装したレコード セットとそうでないものとの違いを理解するのを参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

一部のデータベース管理システム (Dbms) を使用すると、定義済みクエリを作成し、関数のように、プログラムから呼び出すことができます。 クエリは、名前、パラメーターを受け取る可能性があり、レコードを返す可能性があります。 このトピックの手順では、定義済みのクエリのレコードを返します (およびパラメーターを取得) を呼び出す方法について説明します。

データベース クラスでは、定義済みのクエリを更新することはできません。 スナップショットの定義済みクエリとダイナセットの定義済みクエリの違いはなく updateability 他のユーザー (または、プログラムでその他のレコード セット) によって行われた変更がレコード セットに表示されるかどうかです。

> [!TIP]
>  定義済みのクエリのレコードは返されませんを呼び出すレコード セットを使用する必要はありません。 以下に示すように SQL ステートメントを準備するが、それを呼び出すことによって実行、`CDatabase`メンバー関数は[ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql)します。

定義済みのクエリを呼び出すために 1 つのレコード セット クラスを作成できますが、自分で作業をいくつか実行する必要があります。 ウィザードでは、この目的専用のクラスを作成することはできません。

#### <a name="to-create-a-class-for-calling-a-predefined-query-stored-procedure"></a>定義済みのクエリを呼び出すためのクラスを作成するには、(ストアド プロシージャ)

1. 使用して、 [MFC ODBC コンシューマー ウィザード](../../mfc/reference/adding-an-mfc-odbc-consumer.md)から**クラスの追加**クエリによって返される列に最も貢献するテーブルのレコード セット クラスを作成します。 これにより、スタートが切れます。

1. 手動でクエリを返しますが、ウィザードが作成されませんでしたが、そのすべてのテーブルの列のフィールド データ メンバーを追加します。

   たとえば、クエリが 2 つのテーブルから 3 つの列を返す場合は、クラスに (適切なデータ型) の 6 つのフィールド データ メンバーを追加します。

1. 手動で追加[RFX](../../data/odbc/record-field-exchange-rfx.md)内の関数呼び出し、 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)クラスには、それぞれのデータ型に対応する 1 つのメンバー関数は、フィールド データ メンバーを追加します。

    ```cpp
    Immediately before these RFX calls, call <MSHelp:link keywords="_mfc_CFieldExchange.3a3a.SetFieldType" TABINDEX="0">SetFieldType</MSHelp:link>, as shown here:
    pFX->SetFieldType( CFieldExchange::outputColumn );
    ```

    > [!NOTE]
    >  データ型と、結果に返される列の順序設定が必要です。 RFX 関数の順序で呼び出す`DoFieldExchange`結果セット列の順序が一致する必要があります。

1. レコード セット クラスのコンス トラクターで、新しいフィールド データ メンバーの初期化を手動で追加します。

   初期化の値を増やす必要がありますも、 [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)データ メンバー。 初期化が書き込まれますが、フィールド データ メンバーの追加のみについて説明します。 例えば:

    ```cpp
    m_nFields += 6;
    ```

   一部のデータ型が初期化できませんここでは、たとえば、`CLongBinary`またはバイト配列。

1. クエリがパラメーターを受け取る場合は、各パラメーター、RFX 関数呼び出しごとに、および各初期化パラメーターのデータ メンバーを追加します。

1. 増やす必要があります`m_nParams`行ったようにパラメーターを追加各`m_nFields`のこの手順の手順 4. でフィールドを追加します。 詳細については、[レコード セット: レコード セット (ODBC) をパラメーター化](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)を参照してください。

1. 次の形式の SQL ステートメントの文字列を手動で作成するには。

    ```
    {CALL proc-name [(? [, ?]...)]}
    ```

   場所**呼び出す**ODBC キーワードで、**プロシージャ名**データ ソースで認識されているクエリの名前は、および"でしょうか"項目 (ある場合)、レコード セットには、実行時に指定のするパラメーター値のプレース ホルダーは、. 次の例では、1 つのパラメーターのプレース ホルダーを準備します。

    ```
    CString mySQL = "{CALL Delinquent_Accts (?)}";
    ```

1. レコード セットが表示されたコード、設定、レコード セットのパラメーターの値のデータ メンバーを呼び出して、`Open`メンバー関数での SQL 文字列を渡す、 *lpszSQL*パラメーター。 によって返される文字列を置き換える代わりに、または、`GetDefaultSQL`クラスのメンバー関数。

次の例は、という名前の定義済みクエリを呼び出すための手順を示します`Delinquent_Accts`、販売地域の数の 1 つのパラメーターを受け取ります。 このクエリは、3 つの列を返します: `Acct_No`、 `L_Name`、`Phone`します。 すべての列では、Customers テーブルからです。

次のレコード セットには、クエリから返されるパラメーターの売上を地域番号の実行時に要求された列のフィールド データ メンバーを指定します。

```cpp
class CDelinquents : public CRecordset
{
// Field/Param Data
    LONG m_lAcct_No;
    CString m_strL_Name;
    CString m_strPhone;
    LONG m_lDistParam;
    // ...
};
```

このクラスの宣言は、ウィザードでは、それを書き込む以外の`m_lDistParam`メンバーが手動で追加されました。 ここで他のメンバーは表示されません。

次の例では、データ メンバーの初期化、`CDelinquents`コンス トラクター。

```cpp
CDelinquents::CDelinquents(CDatabase* pdb)
   : CRecordset(pdb)
{
    // Wizard-generated params:
    m_lAcct_No = 0;
    m_strL_Name = "";
    m_strPhone = "";
    m_nFields = 3;
    // User-defined params:
    m_nParams = 1;
    m_lDistParam = 0;
}
```

初期化に注意してください[m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)と[m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)します。 ウィザードを初期化します`m_nFields`; を初期化する`m_nParams`します。

次の例では、RFX 関数`CDelinquents::DoFieldExchange`:

```cpp
void CDelinquents::DoFieldExchange(CFieldExchange* pFX)
{
    pFX->SetFieldType(CFieldExchange::outputColumn);
    RFX_Long(pFX, "Acct_No", m_lAcct_No);
    RFX_Text(pFX, "L_Name", m_strL_Name);
    RFX_Text(pFX, "Phone", m_strPhone);
    pFX->SetFieldType(CFieldExchange::param);
    RFX_Long(pFX, "Dist_No", m_lDistParam);
}
```

次の 3 つの返される列の rfx 関数の呼び出しを行うだけでなく、このコードは実行時に渡すパラメーターのバインドを管理します。 パラメーターはキーを設定する、 `Dist_No` (地域番号) の列。

次の例では、SQL 文字列を設定する方法と、レコード セットを開くために使用する方法を示します。

```cpp
// Construct a CDelinquents recordset object
CDelinquents rsDel( NULL );
CString strSQL = "{CALL Delinquent_Accts (?)}"
// Specify a parameter value (obtained earlier from the user)
rsDel.m_lDistParam = lDistrict;
// Open the recordset and run the query
if( rsDel.Open( CRecordset::snapshot, strSQL ) )
    // Use the recordset ...
```

このコードは、スナップショットを構築、前に、ユーザーから収集したパラメーターを渡し、定義済みのクエリを呼び出します。 クエリを実行すると、指定した販売地域のレコードを返します。 各レコードには、アカウント番号、顧客の姓、名、および顧客の電話番号の列が含まれています。

> [!TIP]
>  ストアド プロシージャからの戻り値 (出力パラメーター) を処理する可能性があります。 詳細と例では、[つ](../../mfc/reference/cfieldexchange-class.md#setfieldtype)を参照してください。

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: クエリの再実行 (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)<br/>
[レコードセット: テーブルにアクセスするレコードセット クラスの宣言 (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)<br/>
[レコードセット: 結合 (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)