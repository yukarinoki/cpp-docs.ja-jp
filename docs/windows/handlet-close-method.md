---
title: Handlet::close メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: 1b9d597c-abcf-4028-a068-0344560009f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7cbe76cdea5c8fadef818ede1d63d88e4437bdae
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39651068"
---
# <a name="handletclose-method"></a>HandleT::Close メソッド
現在の終了**HandleT**オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp  
void Close();  
```  
  
## <a name="remarks"></a>Remarks  
 現在の基になるハンドル**HandleT**が閉じられると**HandleT**無効な状態に設定されています。  
  
 ハンドルが適切に終了しない場合は、呼び出し元のスレッドで例外が発生します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HandleT クラス](../windows/handlet-class.md)