---
title: _com_ptr_t::Detach |Microsoft ドキュメント
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
ms.openlocfilehash: 6fbe8fd203c3fda75e83aee623254676dacaf1da
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32410581"
---
# <a name="comptrtdetach"></a>_com_ptr_t::Detach
**Microsoft 固有の仕様**  
  
 カプセル化されたインターフェイス ポインターを抽出して返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
Interface* Detach( ) throw( );  
  
```  
  
## <a name="remarks"></a>コメント  
 抽出、カプセル化されたインターフェイス ポインターを返し、カプセル化されたポインター ストレージをクリア**NULL**です。 これによって、カプセル化からインターフェイス ポインターが削除されます。 呼び出すかどうかは**リリース**返されたインターフェイス ポインター。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_ptr_t クラス](../cpp/com-ptr-t-class.md)