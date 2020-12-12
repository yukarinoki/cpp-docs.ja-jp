---
description: 詳細については、「プロバイダーでのプロパティの参照」を参照してください。
title: プロバイダーでのプロパティの参照
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB providers, properties
- references, to properties in providers
- referencing properties in providers
ms.assetid: bfbb3851-5eed-467a-a179-4a97a9515525
ms.openlocfilehash: dfc3b06820b98477a033b450d42feca52c5c7a72
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286619"
---
# <a name="referencing-a-property-in-your-provider"></a>プロバイダーでのプロパティの参照

必要なプロパティのプロパティグループとプロパティ ID を検索します。 詳細については、 **OLE DB プログラマーリファレンス** の「 [OLE DB のプロパティ](/previous-versions/windows/desktop/ms722734(v=vs.85))」を参照してください。

次の例では、行セットからプロパティを取得しようとしていることを前提としています。 セッションまたはコマンドを使用するコードは似ていますが、別のインターフェイスを使用しています。

コンストラクターのパラメーターとして、プロパティグループを使用して [CDBPropSet](../../data/oledb/cdbpropset-class.md) オブジェクトを作成します。 次に例を示します。

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);
```

[Addproperty](./cdbpropset-class.md#addproperty)を呼び出し、プロパティに割り当てられるプロパティ ID と値を渡します。 値の型は、使用しているプロパティによって異なります。

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);

propset.AddProperty(DBPROP_IRowsetChange, true);

propset.AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_DELETE);
```

インターフェイスを使用して `IRowset` を呼び出し `GetProperties` ます。 プロパティセットをパラメーターとして渡します。 最終的なコードを次に示します。

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

## <a name="see-also"></a>関連項目

[OLE DB プロバイダーテンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)
