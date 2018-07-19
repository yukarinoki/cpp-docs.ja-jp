---
title: Handlet::close メソッド |Microsoft ドキュメント
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
ms.openlocfilehash: 4f0c1e47420106651cfe0526d6d212e9819a72ff
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873252"
---
# <a name="handletclose-method"></a>HandleT::Close メソッド
現在の HandleT オブジェクトを閉じます。  
  
## <a name="syntax"></a>構文  
  
```  
void Close();  
```  
  
## <a name="remarks"></a>コメント  
 現在 HandleT の基になるハンドルが閉じられるし、HandleT が無効な状態に設定されています。  
  
 ハンドルが正しく閉じられません、呼び出し元のスレッドで例外が発生します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HandleT クラス](../windows/handlet-class.md)