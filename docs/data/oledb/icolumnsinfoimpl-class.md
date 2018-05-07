---
title: IColumnsInfoImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IColumnsInfoImpl<T>
- ATL::IColumnsInfoImpl
- IColumnsInfoImpl
- ATL.IColumnsInfoImpl
- ATL::IColumnsInfoImpl<T>
dev_langs:
- C++
helpviewer_keywords:
- IColumnsInfoImpl class
ms.assetid: ba74c1c5-2eda-4452-8b57-84919fa0d066
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 93cc4c44031d2091de64f2d82c1866135d1702cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="icolumnsinfoimpl-class"></a>IColumnsInfoImpl クラス
実装を提供、 [IColumnsInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx)インターフェイスです。  
  
## <a name="syntax"></a>構文

```cpp
template <class T>  
class ATL_NO_VTABLE IColumnsInfoImpl :   
   public IColumnsInfo,    
   public CDBIDOps  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`IColumnsInfoImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[GetColumnInfo](../../data/oledb/icolumnsinfoimpl-getcolumninfo.md)|ほとんどのコンシューマーが必要な列のメタデータを返します。|  
|[MapColumnIDs](../../data/oledb/icolumnsinfoimpl-mapcolumnids.md)|指定された列の Id によって識別される行セット内の列の序数の配列を返します。|  
  
## <a name="remarks"></a>コメント  
 行セットとコマンドの必須のインターフェイスです。 プロバイダーの動作を変更する`IColumnsInfo`実装では、プロバイダーの列マップを変更する必要があります。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)