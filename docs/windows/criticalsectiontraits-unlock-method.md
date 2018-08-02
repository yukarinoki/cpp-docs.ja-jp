---
title: Criticalsectiontraits::unlock メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 8fb382f5-6eda-407e-9673-71d77bda4962
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2f66f185692c200ea459b88363143c0cc1af9d55
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466011"
---
# <a name="criticalsectiontraitsunlock-method"></a>CriticalSectionTraits::Unlock メソッド
指定のクリティカル セクション オブジェクトの解放の所有権をサポートするように CriticalSection テンプレートを専門としています。  
  
## <a name="syntax"></a>構文  
  
```  
inline static void Unlock(  
   _In_ Type cs  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *cs*  
 クリティカル セクション オブジェクトへのポインター。  
  
## <a name="remarks"></a>Remarks  
 *型*として修飾子が定義されている`typedef CRITICAL_SECTION* Type;`します。  
  
 詳細については、次を参照してください。 Windows API のドキュメントの「同期関数」セクションでは"により function"です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>関連項目  
 [CriticalSectionTraits 構造体](../windows/criticalsectiontraits-structure.md)