---
title: CAccessorBase クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CAccessorBase
dev_langs:
- C++
helpviewer_keywords:
- CAccessorBase class
ms.assetid: 389b65be-11ca-4ae0-9290-60c621c4982b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f598f49d279085b23e0bd3b94c48620363b5a816
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090797"
---
# <a name="caccessorbase-class"></a>CAccessorBase クラス
OLE DB テンプレートのすべてのアクセサーは、このクラスから派生します。 `CAccessorBase` 複数のアクセサーを管理する 1 つの行セットを使用できます。 また、両方のパラメーターと出力列のバインドを提供します。  
  
## <a name="syntax"></a>構文

```cpp
// Replace with syntax  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[閉じる](../../data/oledb/caccessorbase-close.md)|アクセサーを閉じます。|  
|[GetHAccessor](../../data/oledb/caccessorbase-gethaccessor.md)|アクセサー ハンドルを取得します。|  
|[GetNumAccessors](../../data/oledb/caccessorbase-getnumaccessors.md)|クラスで作成したアクセサーの数を取得します。|  
|[IsAutoAccessor](../../data/oledb/caccessorbase-isautoaccessor.md)|指定されたアクセサーが自動かどうかをテストします。|  
|[ReleaseAccessors](../../data/oledb/caccessorbase-releaseaccessors.md)|アクセサーを解放します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)