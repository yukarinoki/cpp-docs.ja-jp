---
title: MutexTraits 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits
dev_langs:
- C++
helpviewer_keywords:
- MutexTraits structure
ms.assetid: 6582df80-b9ba-4892-948f-d572a3b23d54
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0406ec7938a623be7b16e0535e9d2c0c769f8392
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874591"
---
# <a name="mutextraits-structure"></a>MutexTraits 構造体
一般的な特性を定義、[ミュー テックス](../windows/mutex-class1.md)クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
struct MutexTraits : HANDLENullTraits;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[MutexTraits::Unlock メソッド](../windows/mutextraits-unlock-method.md)|共有リソースの排他的に制御を解放します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `HANDLENullTraits`  
  
 `MutexTraits`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Wrappers::HandleTraits 名前空間](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)