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
ms.openlocfilehash: 69f3f2c756d158954676f6fc42941b1b80f4345e
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569919"
---
# <a name="handletclose-method"></a>HandleT::Close メソッド
現在の終了**HandleT**オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```  
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