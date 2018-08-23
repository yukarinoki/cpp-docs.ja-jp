---
title: プロバイダーでのプロパティの参照 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, properties
- references, to properties in providers
- referencing properties in providers
ms.assetid: bfbb3851-5eed-467a-a179-4a97a9515525
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 467fa4812af6957bea249d6f55701e1474a9382d
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42573080"
---
# <a name="referencing-a-property-in-your-provider"></a>プロバイダーでのプロパティの参照
対象のプロパティのプロパティ グループとプロパティの ID を検索します。 詳細については、次を参照してください。 [OLE DB プロパティ](/previous-versions/windows/desktop/ms722734\(v=vs.85\))で、 *OLE DB プログラマーズ リファレンス*します。  
  
 次の例では、行セットからプロパティを取得しようとしていることを前提としています。 セッションまたはコマンドを使用するためのコードは似ていますが、別のインターフェイスを使用します。  
  
 作成、 [CDBPropSet](../../data/oledb/cdbpropset-class.md)オブジェクト コンス トラクターにパラメーターとしてプロパティ グループを使用します。 例えば:  
  
```cpp  
CDBPropSet propset(DBPROPSET_ROWSET);  
```  
  
 呼び出す[AddProperty](../../data/oledb/cdbpropset-addproperty.md)プロパティに割り当てるプロパティ ID と値を渡します。 値の型は、使用しているプロパティに依存します。  
  
```cpp  
CDBPropSet propset(DBPROPSET_ROWSET);  

propset.AddProperty(DBPROP_IRowsetChange, true);  

propset.AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_DELETE);  
```  
  
 使用して、`IRowset`インターフェイスを呼び出す`GetProperties`します。 パラメーターとして設定するプロパティを渡します。 最終的なコードを次に示します。  
  
```cpp  
CAgentRowset<CMyProviderCommand>* pRowset = (CAgentRowset<CMyProviderCommand>*) pThis;  
  
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
 [OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)