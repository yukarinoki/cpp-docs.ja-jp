---
title: プロバイダーのブックマーク サポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IRowsetLocate class, provider support for bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- IRowsetLocate class
- OLE DB providers, bookmark support
ms.assetid: 1b14ccff-4f76-462e-96ab-1aada815c377
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 139956fcd7d9244c486ad37797696817c7080fbd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33112509"
---
# <a name="provider-support-for-bookmarks"></a>プロバイダーのブックマーク サポート
このトピックの例では追加、`IRowsetLocate`へのインターフェイス、`CMyProviderRowset`クラスです。 ほとんどの場合では、既存の COM オブジェクトへのインターフェイスを追加することで起動します。 その後、コンシューマー テンプレートからの呼び出しを追加してテストすることができます。 この例をする方法。  
  
-   プロバイダーへのインターフェイスを追加します。  
  
-   コンシューマーに返される列を動的に決定します。  
  
-   ブックマーク サポートを追加します。  
  
 `IRowsetLocate` インターフェイスは `IRowset` のインターフェイスから継承されます。 追加する、`IRowsetLocate`インターフェイスでは、継承`CMyProviderRowset`から[IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)です。  
  
 追加する、`IRowsetLocate`インターフェイスは、ほとんどのインターフェイスとは少し異なります。 プロバイダー テンプレートを OLE DB を vtable を行うには、派生インターフェイスを処理するテンプレート パラメーターにあります。 次のコードは、新しい継承のリストを示しています。  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
// CMyProviderRowset  
class CMyProviderRowset : public CRowsetImpl< CMyProviderRowset,   
      CTextData, CMyProviderCommand, CAtlArray<CTextData>,   
      CSimpleRow,   
          IRowsetLocateImpl<CMyProviderRowset, IRowsetLocate>>  
```  
  
 4 番目、5 番目と 6 番目のパラメーターがすべて追加します。 この例では、4 番目の既定の設定を使用して 5 番目のパラメーターを指定`IRowsetLocateImpl`6 番目のパラメーターとして。 `IRowsetLocateImpl` 2 つのテンプレート パラメーターを受け取る、OLE DB テンプレート クラスは、: これらをフックするため、`IRowsetLocate`へのインターフェイス、`CMyProviderRowset`クラスです。 ほとんどのインターフェイスを追加するには、この手順をスキップし、[次へ] のいずれかに移動できます。 のみ、`IRowsetLocate`と`IRowsetScroll`インターフェイスは、この方法で処理する必要があります。  
  
 確認する必要があります、`CMyProviderRowset`を呼び出す`QueryInterface`の`IRowsetLocate`インターフェイスです。 行を追加`COM_INTERFACE_ENTRY(IRowsetLocate)`にマップします。 に対するインターフェイス マップ`CMyProviderRowset`が、次のコードに示すように表示されます。  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
typedef CRowsetImpl< CMyProviderRowset, CTextData, CMyProviderCommand, CAtlArray<CTextData>, CSimpleRow, IRowsetLocateImpl<CMyProviderRowset, IRowsetLocate>> _RowsetBaseClass;  
  
BEGIN_COM_MAP(CMyProviderRowset)  
   COM_INTERFACE_ENTRY(IRowsetLocate)  
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)  
END_COM_MAP()  
```  
  
 マップする必要があります、`CRowsetImpl`クラスです。 フックする COM_INTERFACE_ENTRY_CHAIN マクロの追加、`CRowsetImpl`マップします。 また、作成と呼ばれる typedef`RowsetBaseClass`継承情報で構成されます。 この typedef は任意無視してかまいません。  
  
 最後に、ハンドル、 **icolumnsinfo::getcolumnsinfo**呼び出します。 通常、これを行う PROVIDER_COLUMN_ENTRY マクロを使用します。 ただし、コンシューマーはブックマークを使用する場合があります。 プロバイダーは、コンシューマーが、ブックマークを要求するかどうかに応じて返します列を変更できる必要があります。  
  
 処理するために、 **icolumnsinfo::getcolumnsinfo**呼び出し、削除、 **PROVIDER_COLUMN**内のマップ、`CTextData`クラスです。 関数を定義して PROVIDER_COLUMN_MAP マクロ`GetColumnInfo`です。 定義する必要が独自`GetColumnInfo`関数。 関数の宣言は、次のようになります。  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
  
class CTextData  
{  
   ...  
     // NOTE: Be sure you removed the PROVIDER_COLUMN_MAP!  
   static ATLCOLUMNINFO* GetColumnInfo(CMyProviderRowset* pThis,   
        ULONG* pcCols);  
   static ATLCOLUMNINFO* GetColumnInfo(CMyProviderCommand* pThis,   
        ULONG* pcCols);  
...  
};  
```  
  
 次に、実装、`GetColumnInfo`次ファイルで次のように機能します。  
  
```cpp
////////////////////////////////////////////////////////////////////  
// MyProviderRS.cpp  
  
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
  
ATLCOLUMNINFO* CTextData::GetColumnInfo(CMyProviderCommand* pThis,   
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
  
 `GetColumnInfo` 最初に確認するかどうかというプロパティを参照してください**DBPROP_IRowsetLocate**が設定されています。 OLE DB 行セット オブジェクトから省略可能なインターフェイスの各プロパティがあります。 コンシューマーは、これらの省略可能なインターフェイスのいずれかを使用する場合、true にプロパティを設定します。 プロバイダーは、このプロパティを確認し、それに基づく特殊なアクションを実行します。  
  
 実装では、コマンド オブジェクトへのポインターを使用してプロパティを取得します。 `pThis`ポインターが行セットまたはコマンド クラスを表します。 これに渡す必要がここでテンプレートを使用するため、`void`ポインターまたはコードはコンパイルされません。  
  
 列情報を格納する静的な配列を指定します。 コンシューマーはブックマーク列をしない、配列内のエントリが無駄になります。 この配列を動的に割り当てることができますが、適切に破棄されることを確認する必要があります。 この例では、定義し、ADD_COLUMN_ENTRY と ADD_COLUMN_ENTRY_EX マクロを使用して配列に情報を挿入します。 次のコードに示すように、MyProviderRS.H ファイルにマクロを追加できます。  
  
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
  
 コンシューマーでコードをテストするに、いくつかの変更を加える必要があります、`OnRun`ハンドラー。 関数に対する最初の変更は、プロパティ、プロパティ セットを追加するコードを追加することです。 コード セット、 **DBPROP_IRowsetLocate**プロパティは、プロバイダーのブックマーク列を表示することをします。 `OnRun`ハンドラー コードは次のように記述する必要があります。  
  
```cpp
//////////////////////////////////////////////////////////////////////  
// TestProv Consumer Application in TestProvDlg.cpp  
  
void CTestProvDlg::OnRun()   
{  
   CCommand<CAccessor<CProvider>> table;  
   CDataSource source;  
   CSession   session;  
  
   if (source.Open("MyProvider.MyProvider.1", NULL, NULL, NULL,   
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
  
 While ループには呼び出すコードが含まれています、`Compare`メソッドで、`IRowsetLocate`インターフェイスです。 まったく同じブックマークを比較するため、コードがある場合は常に成功します。 また、1 つのブックマークを格納、一時変数ように while の後に行うこともできますループに呼び出しが完了すると、`MoveToBookmark`コンシューマー テンプレート内の関数。 `MoveToBookmark`関数呼び出し、`GetRowsAt`メソッド`IRowsetLocate`です。  
  
 また、コンシューマーでユーザー レコードを更新する必要があります。 ブックマークおよび内のエントリを処理するクラスにエントリを追加、 **COLUMN_MAP**:  
  
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
  
 コードを更新したら、ビルドおよびを使用してプロバイダーを実行するはずの`IRowsetLocate`インターフェイスです。  
  
## <a name="see-also"></a>関連項目  
 [高度なプロバイダー手法](../../data/oledb/advanced-provider-techniques.md)