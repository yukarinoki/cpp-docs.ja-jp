---
title: _com_ptr_t::Detach |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method [C++]
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cf38e433f7042707b502a4cba2088db9412adb29
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405835"
---
# <a name="comptrtdetach"></a>_com_ptr_t::Detach
**Microsoft 固有の仕様**  
  
 カプセル化されたインターフェイス ポインターを抽出して返します。  
  
## <a name="syntax"></a>構文  
  
```  
Interface* Detach( ) throw( );  
```  
  
## <a name="remarks"></a>Remarks  
 抽出し、カプセル化されたインターフェイス ポインターを返しますを NULL にカプセル化されたポインター ストレージをクリアします。 これによって、カプセル化からインターフェイス ポインターが削除されます。 呼び出すかどうかは`Release`返されたインターフェイス ポインター。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_ptr_t クラス](../cpp/com-ptr-t-class.md)