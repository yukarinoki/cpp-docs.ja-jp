---
description: 詳細については、「コンシューマーに返される列を動的に判断する」を参照してください。
title: コンシューマーに返される列の動的な判断
ms.date: 10/26/2018
helpviewer_keywords:
- bookmarks [C++], dynamically determining columns
- dynamically determining columns [C++]
ms.assetid: 58522b7a-894e-4b7d-a605-f80e900a7f5f
ms.openlocfilehash: fd70164edff5b9267e01a891a143920ac4e60a35
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287568"
---
# <a name="dynamically-determining-columns-returned-to-the-consumer"></a>コンシューマーに返される列の動的な判断

PROVIDER_COLUMN_ENTRY マクロは通常、呼び出しを処理し `IColumnsInfo::GetColumnsInfo` ます。 ただし、コンシューマーはブックマークの使用を選択することがあるため、プロバイダーは、コンシューマーがブックマークを要求したかどうかに応じて返される列を変更できる必要があります。

呼び出しを処理するには `IColumnsInfo::GetColumnsInfo` 、関数を定義する PROVIDER_COLUMN_MAP を `GetColumnInfo` `CCustomWindowsFile` *カスタム* の rs-232c のユーザーレコードから削除し、独自の関数の定義に置き換え `GetColumnInfo` ます。

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.H
class CCustomWindowsFile
{
public:
   DWORD dwBookmark;
   static const int iSize = 256;
   TCHAR szCommand[iSize];
   TCHAR szText[iSize];
   TCHAR szCommand2[iSize];
   TCHAR szText2[iSize];
  
   static ATLCOLUMNINFO* GetColumnInfo(void* pThis, ULONG* pcCols);
   bool operator==(const CCustomWindowsFile& am)
   {
      return (lstrcmpi(szCommand, am.szCommand) == 0);
   }
};
```

次に、 `GetColumnInfo` 次のコードに示すように、 *カスタム* の rs-232c に関数を実装します。

`GetColumnInfo` 最初に OLE DB プロパティが設定されているかどうかを確認し `DBPROP_BOOKMARKS` ます。 プロパティを取得するために、は `GetColumnInfo` `pRowset` 行セットオブジェクトにポインター () を使用します。 ポインターは、 `pThis` 行セットを作成したクラスを表します。これは、プロパティマップが格納されているクラスです。 `GetColumnInfo` ポインター `pThis` へのポインターを typecasts し `RCustomRowset` ます。

プロパティを確認するために、はインターフェイスを `DBPROP_BOOKMARKS` `GetColumnInfo` 使用し `IRowsetInfo` ます。これは、インターフェイスでを呼び出すことによって取得でき `QueryInterface` `pRowset` ます。 代わりに、ATL [CComQIPtr](../../atl/reference/ccomqiptr-class.md) メソッドを使用することもできます。

```cpp
////////////////////////////////////////////////////////////////////
// CustomRS.cpp
ATLCOLUMNINFO* CCustomWindowsFile::GetColumnInfo(void* pThis, ULONG* pcCols)
{
   static ATLCOLUMNINFO _rgColumns[5];
   ULONG ulCols = 0;
  
   // Check the property flag for bookmarks; if it is set, set the zero
   // ordinal entry in the column map with the bookmark information.
   CCustomRowset* pRowset = (CCustomRowset*) pThis;
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
         DBTYPE_BYTES, 0, 0, GUID_NULL, CCustomWindowsFile, dwBookmark,
         DBCOLUMNFLAGS_ISBOOKMARK)
         ulCols++;
      }
   }
  
   // Next, set the other columns up.
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Command"), 1, 256, DBTYPE_STR, 0xFF, 0xFF,
      GUID_NULL, CCustomWindowsFile, szCommand)
   ulCols++;
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Text"), 2, 256, DBTYPE_STR, 0xFF, 0xFF,
      GUID_NULL, CCustomWindowsFile, szText)
   ulCols++;
  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Command2"), 3, 256, DBTYPE_STR, 0xFF, 0xFF,
      GUID_NULL, CCustomWindowsFile, szCommand2)
   ulCols++;
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Text2"), 4, 256, DBTYPE_STR, 0xFF, 0xFF,
      GUID_NULL, CCustomWindowsFile, szText2)
   ulCols++;
  
   if (pcCols != NULL)
      *pcCols = ulCols;
  
   return _rgColumns;
}
```

この例では、静的配列を使用して列情報を保持します。 コンシューマーがブックマーク列を必要としない場合は、配列内の1つのエントリが使用されません。 この情報を処理するには、ADD_COLUMN_ENTRY と ADD_COLUMN_ENTRY_EX の2つの配列マクロを作成します。 ブックマーク列を指定する場合、ADD_COLUMN_ENTRY_EX には追加のパラメーター、 *フラグ* が必要です。

```cpp
////////////////////////////////////////////////////////////////////////  
// CustomRS.h  
  
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

関数で `GetColumnInfo` は、bookmark マクロは次のように使用されます。

```cpp
ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),
   DBTYPE_BYTES, 0, 0, GUID_NULL, CAgentMan, dwBookmark,
   DBCOLUMNFLAGS_ISBOOKMARK)
```

これで、拡張されたプロバイダーをコンパイルして実行できるようになりました。 プロバイダーをテストするには、「 [単純なコンシューマーの実装](../../data/oledb/implementing-a-simple-consumer.md)」の説明に従ってテストコンシューマーを変更します。 プロバイダーを使用してテストコンシューマーを実行し、テストコンシューマーがプロバイダーから適切な文字列を取得することを確認します。

## <a name="see-also"></a>関連項目

[単純な Read-Only プロバイダーの拡張](../../data/oledb/enhancing-the-simple-read-only-provider.md)<br/>
