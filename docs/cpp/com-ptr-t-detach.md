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
ms.openlocfilehash: c07a9ce1d315c6738472850b987ccb397feda267
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37941354"
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