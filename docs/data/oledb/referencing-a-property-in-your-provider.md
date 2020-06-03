---
title: プロバイダーでのプロパティの参照
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB providers, properties
- references, to properties in providers
- referencing properties in providers
ms.assetid: bfbb3851-5eed-467a-a179-4a97a9515525
ms.openlocfilehash: d70a1901c457d9fbdbe8712d84999e256a54d0c2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209779"
---
# <a name="referencing-a-property-in-your-provider"></a>プロバイダーでのプロパティの参照

必要なプロパティのプロパティグループとプロパティ ID を検索します。 詳細については、 **OLE DB プログラマーリファレンス**の「 [OLE DB のプロパティ](/previous-versions/windows/desktop/ms722734(v=vs.85))」を参照してください。

次の例では、行セットからプロパティを取得しようとしていることを前提としています。 セッションまたはコマンドを使用するコードは似ていますが、別のインターフェイスを使用しています。

コンストラクターのパラメーターとして、プロパティグループを使用して[CDBPropSet](../../data/oledb/cdbpropset-class.md)オブジェクトを作成します。 次に例を示します。

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);
```

[Addproperty](../../data/oledb/cdbpropset-addproperty.md)を呼び出し、プロパティに割り当てられるプロパティ ID と値を渡します。 値の型は、使用しているプロパティによって異なります。

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);

propset.AddProperty(DBPROP_IRowsetChange, true);

propset.AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_DELETE);
```

`IRowset` インターフェイスを使用して `GetProperties`を呼び出します。 プロパティセットをパラメーターとして渡します。 最終的なコードを次に示します。

```cpp
CAgentRowset<CCustomCommand>* pRowset = (CAgentRowset<CCustomCommand>*) pThis;

CComQIPtr<IRowsetInfo, &IID_IRowsetInfo> spRowsetProps = pRowset;

DBPROPIDSET set;
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
      ...  // Use property here
   }
}
```

## <a name="see-also"></a>参照

[OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)
