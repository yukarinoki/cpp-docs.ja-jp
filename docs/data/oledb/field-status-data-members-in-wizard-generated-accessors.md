---
title: ウィザードで生成されたアクセサーのステータス データ メンバーをフィールド |Microsoft Docs
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
ms.openlocfilehash: ce3ad819b6e22bfb5c760849e5f3fdf85bd4f7bc
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49809097"
---
# <a name="field-status-data-members-in-wizard-generated-accessors"></a>ウィザードで生成されたアクセサーのフィールド ステータスのデータ メンバー

ATL OLE DB コンシューマー ウィザードを使用してコンシューマーを作成するときに、ウィザードは、列マップで指定したフィールドごとにユーザー レコード クラスのデータ メンバーを生成します。 各データ メンバーが型の`DWORD`該当するフィールドに対応する状態値が含まれています。  
  
たとえば、データ メンバー *m_OwnerID*、ウィザードは、フィールドの状態の追加のデータ メンバーを生成 (*dwOwnerIDStatus*)、フィールド長のもう 1 つ (*dwOwnerIDLength*). COLUMN_ENTRY_LENGTH_STATUS エントリを含む列のマップも生成されます。  
  
これは、次のコードに示します。  
  
```cpp  
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
> ユーザー レコード クラスを変更するか、独自のコンシューマーを作成する場合、データ変数は、ステータス変数と長さ変数よりも前に記述する必要があります。  
  
状態値は、デバッグ目的で使用できます。 ATL OLE DB コンシューマー ウィザードで生成されたコードでは、コンパイル エラー DB_S_ERRORSOCCURRED または DB_E_ERRORSOCCURRED などを生成する場合、フィールド ステータス データ メンバーの現在の値最初に確認する必要があります。 0 以外の値が指定されている問題のある列に対応しています。  
  
特定のフィールドに NULL 値を設定するのに状態の値を使用することもできます。 これにより、フィールドの値を 0 ではなく、NULL として区別する場合に役立ちます。 NULL が有効な値、または特殊な値かどうかを判断し、アプリケーションが処理する方法を決定する責任です。 OLE DB は、ジェネリック、NULL 値を指定する適切な手段として、DBSTATUS_S_ISNULL を定義します。 コンシューマーは、データを読み取るし、値が null、status フィールドは、DBSTATUS_S_ISNULL に設定されます。 コンシューマーは、NULL 値を設定する場合、コンシューマーは、プロバイダーを呼び出す前に DBSTATUS_S_ISNULL にステータス値を設定します。  
  
次に、Oledb.h と DBSTATUSENUM の検索を開きます。 DBSTATUSENUM 列挙値に対して 0 以外の状態を表す数値を適合できます。 列挙型の名前で何が問題を通知するのに十分でない場合は、"Status"、「データの値をバインドする」のセクションのトピックを参照してください、 [OLE DB プログラマ ガイド](/previous-versions/windows/desktop/ms713643)します。 このトピックには、作業またはデータを設定するときに使用される状態値のテーブルが含まれています。 長さの値については、同じセクションでは、"Length"トピックを参照してください。  
  
## <a name="retrieving-the-length-or-status-of-a-column"></a>長さまたは列のステータスを取得します。  

可変長列の長さ、または (たとえば、DBSTATUS_S_ISNULL の確認) を列のステータスを取得できます。  
  
- 長さを取得するには、COLUMN_ENTRY_LENGTH マクロを使用します。  
  
- 状態を取得するには、COLUMN_ENTRY_STATUS マクロを使用します。  
  
- 両方を取得するには、次に示す COLUMN_ENTRY_LENGTH_STATUS を使用します。  
  
```cpp  
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
  
使用すると`CDynamicAccessor`長さと状態を自動的に連結します。 長さと状態の値を取得する、`GetLength`と`GetStatus`メンバー関数。  
  
## <a name="see-also"></a>関連項目  

[OLE DB コンシューマー テンプレートの操作](../../data/oledb/working-with-ole-db-consumer-templates.md)