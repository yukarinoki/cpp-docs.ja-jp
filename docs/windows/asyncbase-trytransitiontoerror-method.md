---
title: Asyncbase::trytransitiontoerror メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::TryTransitionToError
dev_langs:
- C++
helpviewer_keywords:
- TryTransitionToError method
ms.assetid: f6d11c25-1ce3-43f9-af1c-97c4dc0f6f0f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 97fcade98e82a289c172c7651f62f3de0394fe16
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33863505"
---
# <a name="asyncbasetrytransitiontoerror-method"></a>AsyncBase::TryTransitionToError メソッド
指定したエラー コードが内部エラー状態を変更できるかどうかを示します。  
  
## <a name="syntax"></a>構文  
  
```  
bool TryTransitionToError(  
   const HRESULT error  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `error`  
 エラーの hresult 値。  
  
## <a name="return-value"></a>戻り値  
 `true` 内部エラー状態が変更された場合それ以外の場合、`false`です。  
  
## <a name="remarks"></a>コメント  
 この操作は、エラー状態は S_OK を既に設定されている場合にのみ、エラー状態を変更します。 エラー状態であるエラー、キャンセル、完了すると、または閉じられた場合は、この操作を指定しても効果はありません。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [AsyncBase クラス](../windows/asyncbase-class.md)