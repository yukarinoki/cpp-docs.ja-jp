---
title: フィールド ステータス データ メンバー ウィザードで生成されたアクセサーの |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates, field status
- field status in OLE DB templates
ms.assetid: 66e4e223-c60c-471e-860d-d23abcdfe371
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3f1017c3decacfee223f0e0f89267b192208fe7a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="field-status-data-members-in-wizard-generated-accessors"></a>ウィザードで生成されたアクセサーのフィールド ステータスのデータ メンバー
ATL OLE DB コンシューマー ウィザードを使用してコンシューマーを作成するときに、ウィザードは、ユーザー レコード クラスのマップには、列を指定している各フィールドのデータ メンバーを生成します。 各データ メンバーが型`DWORD`該当するフィールドに対応する状態値が含まれています。  
  
 たとえば、データ メンバー *m_OwnerID*、ウィザードは、フィールドの状態の追加のデータ メンバーを生成 (*dwOwnerIDStatus*) およびフィールドの長さのもう 1 つ (*dwOwnerIDLength*). 生成することも、列マップで`COLUMN_ENTRY_LENGTH_STATUS`エントリです。  
  
 これは、次のコードで示されます。  
  
```  
[db_source("insert connection string")]  
[db_command(" \  
   SELECT \  
      Au_ID, \  
      Author, \  
      `Year Born`, \  
      FROM Authors")]  
  
class CAuthors  
{  
public:  
  
   // The following wizard-generated data members contain status   
   // values for the corresponding fields in the column map. You   
   // can use these values to hold NULL values that the database   
   // returns or to hold error information when the compiler returns   
   // errors. See "Field Status Data Members in Wizard-Generated   
   // Accessors" in the Visual C++ documentation for more information   
   // on using these fields.  
   DWORD m_dwAuIDStatus;  
   DWORD m_dwAuthorStatus;  
   DWORD m_dwYearBornStatus;  
  
   // The following wizard-generated data members contain length  
   // values for the corresponding fields in the column map.  
   DWORD m_dwAuIDLength;  
   DWORD m_dwAuthorLength;  
   DWORD m_dwYearBornLength;  
  
BEGIN_COLUMN_MAP(CAuthorsAccessor)  
   COLUMN_ENTRY_LENGTH_STATUS(1, m_AuID, dwAuIDLength, dwAuIDStatus)  
   COLUMN_ENTRY_LENGTH_STATUS(2, m_Author, dwAuthorLength, dwAuthorStatus)  
   COLUMN_ENTRY_LENGTH_STATUS(3, m_YearBorn, dwYearBornLength, dwYearBornStatus)  
END_COLUMN_MAP()  
  
   [ db_column(1, status=m_dwAuIDStatus, length=m_dwAuIDLength) ] LONG m_AuID;  
   [ db_column(2, status=m_dwAuthorStatus, length=m_dwAuthorLength) ] TCHAR m_Author[51];  
   [ db_column(3, status=m_dwYearBornStatus, length=m_dwYearBornLength) ] SHORT m_YearBorn;  
  
   void GetRowsetProperties(CDBPropSet* pPropSet)  
   {  
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);  
      pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);  
   }  
};  
```  
  
> [!NOTE]
>  ユーザー レコード クラスを変更するか、独自のコンシューマーを作成する場合、データ変数は、ステータス変数と長さ変数よりも前に記述する必要があります。  
  
 デバッグの目的で状態の値を使用することができます。 ATL OLE DB コンシューマー ウィザードで生成されたコードなどのコンパイル エラーを生成する場合**DB_S_ERRORSOCCURRED**または**DB_E_ERRORSOCCURRED**フィールドの状態の現在の値は、まず必要がありますデータ メンバーです。 0 以外の値を持つものは、問題が発生した列に対応しています。  
  
 特定のフィールドに NULL 値を設定するのに状態値を使用することもできます。 これにより、フィールドの値を 0 ではなく、NULL として区別する場合に役立ちます。 ユーザーが自分に NULL が有効な値、または特殊な値かどうかを判断し、アプリケーションが処理する方法を決定します。 OLE DB 定義**DBSTATUS_S_ISNULL**一般的な NULL 値を指定する適切な手段として。 ステータス フィールドが設定されている場合は、コンシューマーがデータを読み取るし、値が null、 **DBSTATUS_S_ISNULL**です。 コンシューマーは、NULL 値を設定する必要がある場合、コンシューマー状態値を設定**DBSTATUS_S_ISNULL**プロバイダーを呼び出す前にします。  
  
 次に、Oledb.h を開き、検索**DBSTATUSENUM**です。 に対して 0 以外の状態を表す数値を一致することができます、 **DBSTATUSENUM**列挙値。 列挙型の名前が何が問題を確認するのに十分でない場合は、"Status"、「データの値をバインドする」のセクションのトピックを参照してください、 [OLE DB プログラマ ガイド](http://go.microsoft.com/fwlink/p/?linkid=121548)です。 このトピックには、作業またはデータを設定するときに使用される状態値のテーブルが含まれています。 長さの値については、同じセクションで「長さ」トピックを参照してください。  
  
## <a name="retrieving-the-length-or-status-of-a-column"></a>長さまたは列のステータスを取得します。  
 可変長列の長さ、または列の状態を取得することができます (をチェックする**DBSTATUS_S_ISNULL**など)。  
  
-   長さを取得するを使用して、`COLUMN_ENTRY_LENGTH`マクロです。  
  
-   ステータスを取得するを使用して、`COLUMN_ENTRY_STATUS`マクロです。  
  
-   両方を取得する`COLUMN_ENTRY_LENGTH_STATUS`、次のようにします。  
  
```  
class CProducts  
{  
public:  
   char      szName[40];  
   long      nNameLength;  
   DBSTATUS   nNameStatus;  
  
BEGIN_COLUMN_MAP(CProducts)  
// Bind the column to CProducts.m_ProductName.  
// nOrdinal is zero-based, so the column number of m_ProductName is 1.  
   COLUMN_ENTRY_LENGTH_STATUS(1, szName, nNameLength, nNameStatus)  
END_COLUMN_MAP()  
};  
  
CTable<CAccessor<CProducts >> product;  
  
product.Open(session, "Product");  

while (product.MoveNext() == S_OK)  
{  
   // Check the product name isn't NULL before tracing it  
   if (product.nNameStatus == DBSTATUS_S_OK)  
      ATLTRACE("%s is %d characters\n", szName, nNameLength);  
}  
```  
  
 使用すると`CDynamicAccessor`長さと状態を自動的に連結します。 長さと状態の値を取得するを使用して、`GetLength`と**GetStatus**メンバー関数。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレートの操作](../../data/oledb/working-with-ole-db-consumer-templates.md)