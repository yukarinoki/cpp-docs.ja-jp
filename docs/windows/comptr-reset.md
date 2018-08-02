---
title: ComPtr::Reset |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: aa6a46f7-f56b-4fd5-add0-7cea55f7abda
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6edbe333ddb634d8657712695250ec627a171780
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461085"
---
# <a name="comptrreset"></a>ComPtr::Reset
これに関連付けられているインターフェイス ポインターのすべての参照を解放**ComPtr**します。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned long Reset();  
```  
  
## <a name="return-value"></a>戻り値  
 解放された参照の数 (存在する場合)。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ComPtr クラス](../windows/comptr-class.md)