---
title: 'レコード セット: 定義済みクエリ (ODBC) クラスの宣言 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets, queries
- predefined queries and recordsets
- stored procedures, and recordsets
- recordsets, predefined queries
- recordsets, stored procedures
ms.assetid: d27c4df9-dad2-4484-ba72-92ab0c8ff928
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cbbb9202aaf56681a792e1acf2a0c02eff5636d9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="recordset-declaring-a-class-for-a-predefined-query-odbc"></a>レコードセット: 定義済みクエリを利用したクラスの宣言 (ODBC)
このトピックの内容は、MFC ODBC クラスに該当します。  
  
 このトピックでは、定義済みクエリ (Microsoft SQL Server と同様に、ストアド プロシージャとも呼ばれます) のレコード セット クラスを作成する方法について説明します。  
  
> [!NOTE]
>  このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。 バルク行フェッチが実装されている場合、プロセスはよく似ています。 バルク行フェッチを実装したレコード セットとそうでないものの違いを理解するのを参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)です。  
  
 一部のデータベース管理システム (Dbms) を使用すると、定義済みクエリを作成し、関数のように、プログラムから呼び出すことができます。 クエリは、名前を持つ、パラメーターを受け取る可能性があり、レコードを返す場合があります。 このトピックの手順では、定義済みクエリのレコードを返します (およびパラメーター) を呼び出す方法を説明します。  
  
 データベース クラスでは、定義済みのクエリを更新することはできません。 定義済みクエリをスナップショットとダイナセットの定義済みクエリの違いはなく updateability 他のユーザー (または、プログラム内の他のレコード セット) によって行われた変更は、レコード セットに表示されるかどうか。  
  
> [!TIP]
>  レコード セットのレコードを返さないクエリを呼び出すをする必要はありません。 以下に示すように SQL ステートメントを準備する場合は、呼び出すことによって実行、`CDatabase`メンバー関数は、 [ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql)です。  
  
 定義済みのクエリを呼び出すために単一のレコード セット クラスを作成することができますが、自分で作業のいくつか行う必要があります。 ウィザードは、この目的専用のクラスの作成をサポートしていません。  
  
#### <a name="to-create-a-class-for-calling-a-predefined-query-stored-procedure"></a>定義済みクエリを呼び出すためのクラスを作成するには、(ストアド プロシージャ)  
  
1.  使用して、 [MFC ODBC コンシューマー ウィザード](../../mfc/reference/adding-an-mfc-odbc-consumer.md)から**クラスの追加**クエリによって返される列が最もを提供しているテーブルのレコード セット クラスを作成します。 これにより、簡単に開始します。  
  
2.  ウィザードを作成できませんでしたが、そのクエリから返されるすべてのテーブルの列のフィールド データ メンバーを手動で追加します。  
  
     たとえば、クエリでは、2 つのテーブルから 3 つの列が返された場合は、クラスに (適切なデータ型) の 6 つのフィールド データ メンバーを追加します。  
  
3.  手動で追加[RFX](../../data/odbc/record-field-exchange-rfx.md)関数呼び出しに、 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)クラスには、それぞれのデータ型に対応する 1 つのメンバー関数は、フィールド データ メンバーを追加します。  
  
    ```  
    Immediately before these RFX calls, call <MSHelp:link keywords="_mfc_CFieldExchange.3a3a.SetFieldType" TABINDEX="0">SetFieldType</MSHelp:link>, as shown here:   
    pFX->SetFieldType( CFieldExchange::outputColumn );  
    ```  
  
    > [!NOTE]
    >  データ型と設定の結果に返される列の順序を知る必要があります。 RFX 関数の順序はで呼び出します`DoFieldExchange`結果セットの列の順序が一致する必要があります。  
  
4.  レコード セット クラスのコンス トラクターで、新しいフィールド データ メンバーの初期化を手動で追加します。  
  
     初期化値を増やす必要がありますも、 [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)データ メンバーです。 初期化が書き込まれますが、する追加のフィールド データ メンバーだけが対象です。 例えば:  
  
    ```  
    m_nFields += 6;  
    ```  
  
     一部のデータ型は初期化できませんここでは、たとえば、`CLongBinary`またはバイト配列。  
  
5.  クエリがパラメーターを受け取る場合は、各パラメーター、RFX 関数呼び出しごとに、および各初期化パラメーターのデータ メンバーを追加します。  
  
6.  インクリメントする必要があります`m_nParams`場合と同様に、パラメーターを追加の各`m_nFields`に対してこの手順の手順 4 でフィールドを追加します。 詳細については、次を参照してください。[レコード セット: レコード セット (ODBC) のパラメーター化](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)です。  
  
7.  次の形式で SQL ステートメントの文字列を手動で作成するには。  
  
    ```  
    {CALL proc-name [(? [, ?]...)]}  
    ```  
  
     場所**を呼び出す**ODBC キーワードで、 **proc 名前**は、データ ソースで認識されている、クエリの名前は、および"?"項目は、(存在する場合)、レコード セットには、実行時に指定のするパラメーター値のプレース ホルダー. 次の例では、1 つのパラメーターのプレース ホルダーを準備します。  
  
    ```  
    CString mySQL = "{CALL Delinquent_Accts (?)}";  
    ```  
  
8.  レコード セットを表示するコード、値を設定、レコード セットのパラメーターのデータ メンバーおよびを呼び出す、**開く**メンバー関数の場合、SQL 文字列を渡します、 **lpszSQL**パラメーター。 代わりに、によって返される文字列を置き換えるか、`GetDefaultSQL`クラスのメンバー関数。  
  
 次の例は、という名前の定義済みクエリを呼び出すための手順を示して`Delinquent_Accts`、販売地域番号の 1 つのパラメーターを受け取ります。 このクエリは、3 つの列を返します: `Acct_No`、 `L_Name`、`Phone`です。 すべての列では、Customers テーブルからです。  
  
 次のレコード セットでは、クエリから返される、sales のパラメーターの地域の実行時に要求された数の列のフィールド データ メンバーを指定します。  
  
```  
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
  
 このクラスの宣言は、ウィザードで生成しを除くと、`m_lDistParam`メンバーが手動で追加されました。 ここで他のメンバーは表示されません。  
  
 次の例では、内のデータ メンバーの初期化、`CDelinquents`コンス トラクターです。  
  
```  
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
  
 初期化に注意してください[m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)と[m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)です。 ウィザードを初期化`m_nFields`; を初期化する`m_nParams`です。  
  
 次の例での RFX 関数の`CDelinquents::DoFieldExchange`:  
  
```  
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
  
 次の 3 つの返される列の RFX を呼び出し、以外は、このコードは、実行時に渡すパラメーターのバインドを管理します。 パラメーターと適合する、 `Dist_No` (district 番号) 列。  
  
 次の例では、SQL 文字列を設定する方法と、レコード セットを開くために使用する方法を示します。  
  
```  
// Construct a CDelinquents recordset object  
CDelinquents rsDel( NULL );  
CString strSQL = "{CALL Delinquent_Accts (?)}"  
// Specify a parameter value (obtained earlier from the user)  
rsDel.m_lDistParam = lDistrict;  
// Open the recordset and run the query  
if( rsDel.Open( CRecordset::snapshot, strSQL ) )  
    // Use the recordset ...  
```  
  
 このコードは、スナップショットを構築、前に、ユーザーから収集したパラメーターを渡し、定義済みのクエリを呼び出します。 クエリを実行すると、指定した販売地域のレコードを返します。 各レコードには、アカウント番号、顧客の姓、および顧客の電話番号の列が含まれています。  
  
> [!TIP]
>  ストアド プロシージャからの戻り値 (出力パラメーター) を処理する可能性があります。 例および詳細については、次を参照してください。[つ](../../mfc/reference/cfieldexchange-class.md#setfieldtype)です。  
  
## <a name="see-also"></a>関連項目  
 [レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)   
 [レコード セット: クエリの再実行 (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)   
 [レコード セット: テーブル (ODBC) クラスの宣言](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)   
 [レコードセット: 結合 (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)