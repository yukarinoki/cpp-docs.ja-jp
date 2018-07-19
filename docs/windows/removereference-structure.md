---
title: RemoveReference 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::RemoveReference
dev_langs:
- C++
helpviewer_keywords:
- RemoveReference structure
ms.assetid: 43ff91bb-815a-440e-b9fb-7dcbb7c863af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 126394e3a63016eccf1f5451d032753bb8f81da8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33881264"
---
# <a name="removereference-structure"></a>RemoveReference 構造体
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
template<class T>  
struct RemoveReference;  
template<class T>  
struct RemoveReference<T&>;  
template<class T>  
struct RemoveReference<T&&>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 クラスです。  
  
## <a name="remarks"></a>コメント  
 指定されたクラス テンプレート パラメーターから参照または右辺値参照の特徴を切り離します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`Type`|クラス テンプレート パラメーターのシノニム。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `RemoveReference`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** internal.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)