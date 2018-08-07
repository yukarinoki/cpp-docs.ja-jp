---
title: Roinitializewrapper::roinitializewrapper コンス トラクター |Microsoft Docs
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
ms.openlocfilehash: 193f0d16b03991e24cb16a90b3310512f6e86054
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39604399"
---
# <a name="roinitializewrapperroinitializewrapper-constructor"></a>RoInitializeWrapper::RoInitializeWrapper コンストラクター
新しいインスタンスを初期化、 **RoInitializeWrapper**クラス。  
  
## <a name="syntax"></a>構文  
  
```cpp  
RoInitializeWrapper(   RO_INIT_TYPE flags)  
```  
  
### <a name="parameters"></a>パラメーター  
 *flags*  
 RO_INIT_TYPE の列挙体は、Windows ランタイムによって提供されるサポートの 1 つ。  
  
## <a name="remarks"></a>Remarks  
 **RoInitializeWrapper**クラスを呼び出す`Windows::Foundation::Initialize(flags)`します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HandleT クラス](../windows/handlet-class.md)