---
title: CDBPropIDSet クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDBPropIDSet
- ATL.CDBPropIDSet
- ATL::CDBPropIDSet
dev_langs:
- C++
helpviewer_keywords:
- CDBPropIDSet class
ms.assetid: 52bb806c-9581-494d-9af7-50d8a4834805
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 67bfd11a46d8e0c852c1881ff8874b7fbd817164
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cdbpropidset-class"></a>CDBPropIDSet クラス
継承、**コンス トラクターは**構造体し、キー フィールドを初期化するコンス トラクターを追加するだけでなく[AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md)メソッドにアクセスします。  
  
## <a name="syntax"></a>構文

```cpp
class CDBPropIDSet : public tagDBPROPIDSET  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md)|プロパティ ID セットにプロパティを追加します。|  
|[CDBPropIDSet](../../data/oledb/cdbpropidset-cdbpropidset.md)|コンストラクターです。|  
|[SetGUID](../../data/oledb/cdbpropidset-setguid.md)|プロパティ ID の GUID を設定します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子 =](../../data/oledb/cdbpropidset-operator-equal.md)|割り当て ID の 1 つのプロパティの内容は、別に設定されます。|  
  
## <a name="remarks"></a>コメント  
 OLE DB コンシューマーを使用して**コンス トラクターは**プロパティ情報を取得するコンシューマーは、これに関するプロパティ Id の配列を渡すための構造体。 1 つの指定されたプロパティ[コンス トラクターは](https://msdn.microsoft.com/en-us/library/ms717981.aspx)構造体が 1 つのプロパティ セットに属しています。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)