---
title: Handlet::handlet コンス トラクター |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::HandleT
dev_langs:
- C++
helpviewer_keywords:
- HandleT, constructor
ms.assetid: 4def6891-7e53-46f1-a197-a80e10744dd5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a0caad909803a0f73987f3e1132920b0948d8d1b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="handlethandlet-constructor"></a>HandleT::HandleT コンストラクター
HandleT クラスの新しいインスタンスを初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
explicit HandleT(  
   typename HandleTraits::Type h =   
      HandleTraits::GetInvalidValue()  
);  
  
HandleT(  
   _Inout_ HandleT&& h  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `h`  
 ハンドル。  
  
## <a name="remarks"></a>コメント  
 最初のコンス トラクターは、オブジェクトへの有効なハンドルではない HandleT オブジェクトを初期化します。 2 番目のコンス トラクターは、パラメーターから新しい HandleT オブジェクトを作成する`h`です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HandleT クラス](../windows/handlet-class.md)