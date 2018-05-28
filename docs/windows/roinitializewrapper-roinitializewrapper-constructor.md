---
title: Roinitializewrapper::roinitializewrapper コンス トラクター |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper
dev_langs:
- C++
ms.assetid: c6f7fb07-14af-4574-9135-cea164607f30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 64f2af40c671760bb8d4e667c209598c46b24665
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="roinitializewrapperroinitializewrapper-constructor"></a>RoInitializeWrapper::RoInitializeWrapper コンストラクター
RoInitializeWrapper クラスの新しいインスタンスを初期化します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
RoInitializeWrapper(   RO_INIT_TYPE flags)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `flags`  
 RO_INIT_TYPE の列挙体は、Windows ランタイムによって提供されるサポートを指定の 1 つ。  
  
## <a name="remarks"></a>コメント  
 RoInitializeWrapper クラスが Windows::Foundation::Initialize を呼び出します (*フラグ*)。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HandleT クラス](../windows/handlet-class.md)