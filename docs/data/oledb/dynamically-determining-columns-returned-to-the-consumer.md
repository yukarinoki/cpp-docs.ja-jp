---
title: コンシューマーに返される列を動的に判断 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- bookmarks [C++], dynamically determining columns
- dynamically determining columns [C++]
ms.assetid: 58522b7a-894e-4b7d-a605-f80e900a7f5f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fd84b6f9451e924fac9e3630df38719c83ff583a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33107940"
---
# <a name="dynamically-determining-columns-returned-to-the-consumer"></a>コンシューマーに返される列の動的な判断
PROVIDER_COLUMN_ENTRY マクロの通常の処理、 **icolumnsinfo::getcolumnsinfo**呼び出します。 ただし、ため、コンシューマーは、ブックマークを選ぶことも、プロバイダーは、コンシューマーが、ブックマークを要求するかどうかによって返される列を変更することでする必要があります。  
  
 処理するために、 **icolumnsinfo::getcolumnsinfo**呼び出し、関数を定義すると、PROVIDER_COLUMN_MAP 削除`GetColumnInfo`から、`CAgentMan`ユーザー myproviderrs.h を記録し、独自の定義に置き換えます`GetColumnInfo`関数。  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
class CAgentMan  
{  
public:  
   DWORD dwBookmark;  
   TCHAR szCommand[256];  
   TCHAR szText[256];  
   TCHAR szCommand2[256];  
   TCHAR szText2[256];  
  
   static ATLCOLUMNINFO* GetColumnInfo(void* pThis, ULONG* pcCols);  
   bool operator==(const CAgentMan& am)  
   {  
      return (lstrcmpi(szCommand, am.szCommand) == 0);  
   }  
  
};  
```  
  
 次に、実装、`GetColumnInfo`次のコードに示すように、次の機能です。  
  
 `GetColumnInfo` かどうかをまずチェックを OLE DB プロパティの**DBPROP_BOOKMARKS**が設定されています。 プロパティを取得する`GetColumnInfo`へのポインターを使用して (`pRowset`)、行セット オブジェクトにします。 `pThis`ポインターは、プロパティ マップが格納されているクラスは、行セットを作成するクラスを表します。 `GetColumnInfo` 丸めない、`pThis`へのポインター、`RMyProviderRowset`ポインター。  
  
 確認する、 **DBPROP_BOOKMARKS**プロパティ、`GetColumnInfo`を使用して、`IRowsetInfo`インターフェイスを呼び出すことによって取得できます`QueryInterface`上、`pRowset`インターフェイスです。 ATL を使用する代わりに、 [CComQIPtr](../../atl/reference/ccomqiptr-class.md)メソッド代わりにします。  
  
```cpp
////////////////////////////////////////////////////////////////////  
// MyProviderRS.cpp  
ATLCOLUMNINFO* CAgentMan::GetColumnInfo(void* pThis, ULONG* pcCols)  
{  
   static ATLCOLUMNINFO _rgColumns[5];  
   ULONG ulCols = 0;  
  
   // Check the property flag for bookmarks; if it is set, set the zero   
   // ordinal entry in the column map with the bookmark information.  
   CAgentRowset* pRowset = (CAgentRowset*) pThis;  
   CComQIPtr<IRowsetInfo, &IID_IRowsetInfo> spRowsetProps = pRowset;  
  
   CDBPropIDSet set(DBPROPSET_ROWSET);  
   set.AddPropertyID(DBPROP_BOOKMARKS);  
   DBPROPSET* pPropSet = NULL;  
   ULONG ulPropSet = 0;  
   HRESULT hr;  
  
   if (spRowsetProps)  
      hr = spRowsetProps->GetProperties(1, &set, &ulPropSet, &pPropSet);  
  
   if (pPropSet)  
   {  
      CComVariant var = pPropSet->rgProperties[0].vValue;  
      CoTaskMemFree(pPropSet->rgProperties);  
      CoTaskMemFree(pPropSet);  
  
      if (SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE))  
      {  
         ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),   
         DBTYPE_BYTES, 0, 0, GUID_NULL, CAgentMan, dwBookmark,   
         DBCOLUMNFLAGS_ISBOOKMARK)  
         ulCols++;  
      }  
   }  
  
   // Next, set the other columns up.  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Command"), 1, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szCommand)  
   ulCols++;  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Text"), 2, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szText)  
   ulCols++;  
  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Command2"), 3, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szCommand2)  
   ulCols++;  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Text2"), 4, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szText2)  
   ulCols++;  
  
   if (pcCols != NULL)  
      *pcCols = ulCols;  
  
   return _rgColumns;  
}  
```  
  
 この例では、静的な配列を使用して、列情報を格納します。 コンシューマーがブックマーク列をしない場合は、配列内の 1 つのエントリは使用されません。 情報を処理するために 2 つの配列マクロを作成する: ADD_COLUMN_ENTRY と ADD_COLUMN_ENTRY_EX です。 ADD_COLUMN_ENTRY_EX で追加のパラメーターを受け取る`flags`、つまりブックマーク列を指定する場合に必要です。  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
#define ADD_COLUMN_ENTRY(ulCols, name, ordinal, colSize, type, precision, scale, guid, dataClass, member) \  
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \  
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \  
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \  
   _rgColumns[ulCols].dwFlags = 0; \  
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \  
   _rgColumns[ulCols].wType = (DBTYPE)type; \  
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \  
   _rgColumns[ulCols].bScale = (BYTE)scale; \  
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member);  
  
#define ADD_COLUMN_ENTRY_EX(ulCols, name, ordinal, colSize, type, precision, scale, guid, dataClass, member, flags) \  
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \  
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \  
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \  
   _rgColumns[ulCols].dwFlags = flags; \  
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \  
   _rgColumns[ulCols].wType = (DBTYPE)type; \  
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \  
   _rgColumns[ulCols].bScale = (BYTE)scale; \  
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member); \  
   memset(&(_rgColumns[ulCols].columnid), 0, sizeof(DBID)); \  
   _rgColumns[ulCols].columnid.uName.pwszName = (LPOLESTR)name;  
```  
  
 `GetColumnInfo`関数、ブックマークのマクロは、次のように使用します。  
  
```  
ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),  
   DBTYPE_BYTES, 0, 0, GUID_NULL, CAgentMan, dwBookmark,   
   DBCOLUMNFLAGS_ISBOOKMARK)  
```  
  
 コンパイルを拡張プロバイダーを実行できます。 プロバイダーをテストするにはテスト コンシューマーを」の説明に従って変更[単純なコンシューマーを実装する](../../data/oledb/implementing-a-simple-consumer.md)です。 プロバイダーをテスト コンシューマーを実行します。 クリックすると、テストのコンシューマーが、プロバイダーから適切な文字列を取得することを確認、**実行**ボタンをクリックして、**テスト コンシューマー**  ダイアログ ボックス。  
  
## <a name="see-also"></a>関連項目  
 [単純な読み取り専用プロバイダーの機能の拡張](../../data/oledb/enhancing-the-simple-read-only-provider.md)