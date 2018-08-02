---
title: Chaininterfaces::iidcount 定数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::IidCount
dev_langs:
- C++
helpviewer_keywords:
- IidCount constant
ms.assetid: d4a90aa0-513c-4e99-b978-e12149734936
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6d089e9639d83150e501b32577de94fc43b516c1
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463942"
---
# <a name="chaininterfacesiidcount-constant"></a>ChainInterfaces::IidCount 定数
インターフェイスのテンプレート パラメーターで指定されたインターフェイスに含まれている Id の合計数*I0*を通じて*I9*します。  
  
## <a name="syntax"></a>構文  
  
```  
static const unsigned long IidCount = Details::InterfaceTraits<I0>::IidCount + Details::InterfaceTraits<I1>::IidCount + Details::InterfaceTraits<I2>::IidCount + Details::InterfaceTraits<I3>::IidCount + Details::InterfaceTraits<I4>::IidCount + Details::InterfaceTraits<I5>::IidCount + Details::InterfaceTraits<I6>::IidCount + Details::InterfaceTraits<I7>::IidCount + Details::InterfaceTraits<I8>::IidCount + Details::InterfaceTraits<I9>::IidCount;  
```  
  
## <a name="return-value"></a>戻り値  
 インターフェイス Id の合計数。  
  
## <a name="remarks"></a>Remarks  
 テンプレート パラメーター *I0*と*I1*が必要なパラメーターと*I2*を通じて*I9*は省略可能です。通常、各インターフェイスの IID の数は、1 になります。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ChainInterfaces 構造体](../windows/chaininterfaces-structure.md)