---
title: CDBPropSet クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDBPropSet
- ATL.CDBPropSet
- ATL::CDBPropSet
dev_langs:
- C++
helpviewer_keywords:
- CDBPropSet class
ms.assetid: 54190149-c277-4679-b81a-ef484d4d1c00
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8d75715ed0dc65fbbf5b581bfea48816e5bd00ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cdbpropset-class"></a>CDBPropSet クラス
継承、 **DBPROPSET**構造体し、キー フィールドを初期化するコンス トラクターを追加するだけでなく`AddProperty`メソッドにアクセスします。  
  
## <a name="syntax"></a>構文

```cpp
class CDBPropSet : public tagDBPROPSET  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[AddProperty](../../data/oledb/cdbpropset-addproperty.md)|プロパティ セットに、プロパティを追加します。|  
|[CDBPropSet](../../data/oledb/cdbpropset-cdbpropset.md)|コンストラクターです。|  
|[SetGUID](../../data/oledb/cdbpropset-setguid.md)|セット、**コンス トラクターは**のフィールド、 **DBPROPSET**構造体。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子 =](../../data/oledb/cdbpropset-operator-equal.md)|1 つのプロパティ セットを他の内容を割り当てます。|  
  
## <a name="remarks"></a>コメント  
 OLE DB プロバイダーとコンシューマーの使用**DBPROPSET**構造体の配列を渡す`DBPROP`構造体。 各`DBPROP`構造体を設定できる 1 つのプロパティを表します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CDBPropIDSet クラス](../../data/oledb/cdbpropidset-class.md)   
 [DBPROPSET 構造体](https://msdn.microsoft.com/en-us/library/ms714367.aspx)   
 [DBPROP 構造体](https://msdn.microsoft.com/en-us/library/ms717970.aspx)