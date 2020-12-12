---
description: 詳細については、「プロバイダーによるブックマークのサポート」を参照してください。
title: プロバイダーのブックマーク サポート
ms.date: 11/04/2016
helpviewer_keywords:
- IRowsetLocate class, provider support for bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- IRowsetLocate class
- OLE DB providers, bookmark support
ms.assetid: 1b14ccff-4f76-462e-96ab-1aada815c377
ms.openlocfilehash: 0a2225f44d9d094f52e97b88eb58c6942906edf6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286658"
---
# <a name="provider-support-for-bookmarks"></a>プロバイダーのブックマーク サポート

このトピックの例では、 `IRowsetLocate` クラスにインターフェイスを追加し `CCustomRowset` ます。 ほとんどの場合、まず、既存の COM オブジェクトにインターフェイスを追加します。 その後、コンシューマーテンプレートから呼び出しをさらに追加してテストできます。 この例では、次の方法を示します。

- プロバイダーにインターフェイスを追加します。

- コンシューマーに返す列を動的に決定します。

- ブックマークサポートを追加します。

`IRowsetLocate` インターフェイスは `IRowset` インターフェイスを継承します。 インターフェイスを追加するに `IRowsetLocate` は `CCustomRowset` 、 [IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)から継承します。

インターフェイスの追加 `IRowsetLocate` は、ほとんどのインターフェイスとは少し異なります。 Vtable をアップさせるために、OLE DB プロバイダーテンプレートには、派生インターフェイスを処理するテンプレートパラメーターがあります。 次のコードは、新しい継承リストを示しています。

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.h

// CCustomRowset
class CCustomRowset : public CRowsetImpl< CCustomRowset,
      CTextData, CCustomCommand, CAtlArray<CTextData>,
      CSimpleRow,
          IRowsetLocateImpl<CCustomRowset, IRowsetLocate>>
```

4番目、5番目、および6番目のパラメーターがすべて追加されます。 この例では、4番目と5番目のパラメーターに既定値を使用しますが、6番目のパラメーターとしてを指定し `IRowsetLocateImpl` ます。 `IRowsetLocateImpl` は、2つのテンプレートパラメーターを受け取る OLE DB テンプレートクラスです。これらは、インターフェイスをクラスにフックします `IRowsetLocate` `CCustomRowset` 。 ほとんどのインターフェイスを追加するには、この手順をスキップし、次のインターフェイスに移動します。 `IRowsetLocate` `IRowsetScroll` インターフェイスとインターフェイスだけをこの方法で処理する必要があります。

次に、がインターフェイスを `CCustomRowset` 呼び出すようにに指示する必要があり `QueryInterface` `IRowsetLocate` ます。 `COM_INTERFACE_ENTRY(IRowsetLocate)`マップに線を追加します。 次のコードに示すように、のインターフェイスマップ `CCustomRowset` が表示されます。

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.h

typedef CRowsetImpl< CCustomRowset, CTextData, CCustomCommand, CAtlArray<CTextData>, CSimpleRow, IRowsetLocateImpl<CCustomRowset, IRowsetLocate>> _RowsetBaseClass;

BEGIN_COM_MAP(CCustomRowset)
   COM_INTERFACE_ENTRY(IRowsetLocate)
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)
END_COM_MAP()
```

また、マップをクラスにフックする必要もあり `CRowsetImpl` ます。 COM_INTERFACE_ENTRY_CHAIN マクロにを追加して、マップにフックし `CRowsetImpl` ます。 また、継承情報で構成されるという名前の typedef を作成し `RowsetBaseClass` ます。 この typedef は任意であり、無視することができます。

最後に、呼び出しを処理し `IColumnsInfo::GetColumnsInfo` ます。 通常は、PROVIDER_COLUMN_ENTRY マクロを使用してこれを行います。 ただし、コンシューマーはブックマークを使用することもできます。 コンシューマーがブックマークを要求したかどうかによって、プロバイダーから返される列を変更できる必要があります。

呼び出しを処理するには `IColumnsInfo::GetColumnsInfo` 、クラスの PROVIDER_COLUMN マップを削除し `CTextData` ます。 PROVIDER_COLUMN_MAP マクロは関数を定義し `GetColumnInfo` ます。 独自の `GetColumnInfo` 関数を定義します。 関数の宣言は次のようになります。

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.H

class CTextData
{
   ...
     // NOTE: Be sure you removed the PROVIDER_COLUMN_MAP!
   static ATLCOLUMNINFO* GetColumnInfo(CCustomRowset* pThis,
        ULONG* pcCols);
   static ATLCOLUMNINFO* GetColumnInfo(CCustomCommand* pThis,
        ULONG* pcCols);
...
};
```

次に、次のように、 `GetColumnInfo` *カスタム* の RS .cpp ファイルに関数を実装します。

```cpp
////////////////////////////////////////////////////////////////////
// CustomRS.cpp

template <class TInterface>
ATLCOLUMNINFO* CommonGetColInfo(IUnknown* pPropsUnk, ULONG* pcCols)
{
   static ATLCOLUMNINFO _rgColumns[5];
   ULONG ulCols = 0;

   CComQIPtr<TInterface> spProps = pPropsUnk;

   CDBPropIDSet set(DBPROPSET_ROWSET);
   set.AddPropertyID(DBPROP_BOOKMARKS);
   DBPROPSET* pPropSet = NULL;
   ULONG ulPropSet = 0;
   HRESULT hr;

   if (spProps)
      hr = spProps->GetProperties(1, &set, &ulPropSet, &pPropSet);

   // Check the property flag for bookmarks, if it is set, set the
// zero ordinal entry in the column map with the bookmark
// information.

   if (pPropSet)
   {
      CComVariant var = pPropSet->rgProperties[0].vValue;
      CoTaskMemFree(pPropSet->rgProperties);
      CoTaskMemFree(pPropSet);

      if ((SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE)))
      {
         ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0,
                     sizeof(DWORD), DBTYPE_BYTES,
            0, 0, GUID_NULL, CAgentMan, dwBookmark,
                        DBCOLUMNFLAGS_ISBOOKMARK)
         ulCols++;
      }
   }

   // Next set the other columns up.
   ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Field1"), 1, 16, DBTYPE_STR,
          0xFF, 0xFF, GUID_NULL, CTextData, szField1)
   ulCols++;
   ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Field2"), 2, 16, DBTYPE_STR,
       0xFF, 0xFF, GUID_NULL, CTextData, szField2)
   ulCols++;

   if (pcCols != NULL)
      *pcCols = ulCols;

   return _rgColumns;
}

ATLCOLUMNINFO* CTextData::GetColumnInfo(CCustomCommand* pThis,
     ULONG* pcCols)
{
   return CommonGetColInfo<ICommandProperties>(pThis->GetUnknown(),
        pcCols);
}

ATLCOLUMNINFO* CAgentMan::GetColumnInfo(RUpdateRowset* pThis, ULONG* pcCols)
{
   return CommonGetColInfo<IRowsetInfo>(pThis->GetUnknown(), pcCols);
}
```

`GetColumnInfo` は、というプロパティが設定されているかどうかを最初に確認し `DBPROP_IRowsetLocate` ます。 OLE DB には、行セットオブジェクトの外部にあるオプションの各インターフェイスのプロパティがあります。 これらのオプションのインターフェイスのいずれかをコンシューマーが使用する場合は、プロパティを true に設定します。 プロバイダーは、このプロパティを確認し、それに基づいて特別な操作を行うことができます。

実装では、command オブジェクトへのポインターを使用してプロパティを取得します。 ポインターは、 `pThis` 行セットまたはコマンドクラスを表します。 ここではテンプレートを使用するため、をポインターとして渡す **`void`** か、コードをコンパイルしないようにする必要があります。

列情報を格納する静的配列を指定します。 コンシューマーがブックマーク列を必要としない場合、配列内のエントリは無駄になります。 この配列は動的に割り当てることができますが、正しく破棄されるようにする必要があります。 この例では、マクロ ADD_COLUMN_ENTRY と ADD_COLUMN_ENTRY_EX を定義して使用し、情報を配列に挿入します。 *カスタム* RS にマクロを追加できます。H ファイルを次のコードに示します。

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

コンシューマーでコードをテストするには、ハンドラーにいくつかの変更を加える必要があり `OnRun` ます。 関数に対する最初の変更として、プロパティセットにプロパティを追加するコードを追加します。 このコードでは、プロパティを true に設定して、 `DBPROP_IRowsetLocate` ブックマーク列を必要とするプロバイダーに指示します。 ハンドラーコードは次のように `OnRun` なります。

```cpp
//////////////////////////////////////////////////////////////////////
// TestProv Consumer Application in TestProvDlg.cpp

void CTestProvDlg::OnRun()
{
   CCommand<CAccessor<CProvider>> table;
   CDataSource source;
   CSession   session;

   if (source.Open("Custom.Custom.1", NULL, NULL, NULL,
          NULL) != S_OK)
      return;

   if (session.Open(source) != S_OK)
      return;

   CDBPropSet propset(DBPROPSET_ROWSET);
   propset.AddProperty(DBPROP_IRowsetLocate, true);
   if (table.Open(session, _T("c:\\public\\testprf2\\myData.txt"),
          &propset) != S_OK)
      return;

   CBookmark<4> tempBookmark;
   ULONG ulCount=0;
   while (table.MoveNext() == S_OK)
   {

      DBCOMPARE compare;
      if (ulCount == 2)
         tempBookmark = table.bookmark;

HRESULT hr = table.Compare(table.dwBookmark, table.dwBookmark,
                 &compare);
      if (FAILED(hr))
         ATLTRACE(_T("Compare failed: 0x%X\n"), hr);
      else
         _ASSERTE(compare == DBCOMPARE_EQ);

      m_ctlString1.AddString(table.szField1);
      m_ctlString2.AddString(table.szField2);
      ulCount++;
   }

   table.MoveToBookmark(tempBookmark);
   m_ctlString1.AddString(table.szField1);
   m_ctlString2.AddString(table.szField2);
}
```

ループには、 **`while`** インターフェイスのメソッドを呼び出すコードが含まれてい `Compare` `IRowsetLocate` ます。 まったく同じブックマークを比較しているので、コードは常にを渡す必要があります。 また、1つのブックマークを一時変数に格納して、ループが終了した後で **`while`** `MoveToBookmark` コンシューマーテンプレート内の関数を呼び出すために使用できるようにします。 関数は、 `MoveToBookmark` `GetRowsAt` でメソッドを呼び出し `IRowsetLocate` ます。

コンシューマーのユーザーレコードも更新する必要があります。 COLUMN_MAP のブックマークとエントリを処理するエントリをクラスに追加します。

```cpp
///////////////////////////////////////////////////////////////////////
// TestProvDlg.cpp

class CProvider
{
// Attributes
public:
   CBookmark<4>    bookmark;  // Add this line
   char   szCommand[16];
   char   szText[256];

   // Binding Maps
BEGIN_ACCESSOR_MAP(CProvider, 1)
   BEGIN_ACCESSOR(0, true)   // auto accessor
      BOOKMARK_ENTRY(bookmark)  // Add this line
      COLUMN_ENTRY(1, szField1)
      COLUMN_ENTRY(2, szField2)
   END_ACCESSOR()
END_ACCESSOR_MAP()
};
```

コードを更新すると、インターフェイスを使用してプロバイダーをビルドして実行できるようになり `IRowsetLocate` ます。

## <a name="see-also"></a>関連項目

[高度なプロバイダー手法](../../data/oledb/advanced-provider-techniques.md)
