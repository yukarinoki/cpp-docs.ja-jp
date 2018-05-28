---
title: Asyncbase::close メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: a52b1124-754b-4393-b491-64aae0c22f1c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4f3f36656b9316fb6ad980349a836fad31c3a9a0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="asyncbaseclose-method"></a>AsyncBase::Close メソッド
非同期操作を閉じます。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHOD(  
   Close  
)(void) override;  
```  
  
## <a name="return-value"></a>戻り値  
 操作が終了またはである場合は S_OK が閉じられました。それ以外の場合、E_ILLEGAL_STATE_CHANGE です。  
  
## <a name="remarks"></a>コメント  
 Close() は、IAsyncInfo::Close の既定の実装は、実際の作業は行われません。 実際には、非同期操作を閉じます OnClose() 純粋仮想メソッドをオーバーライドします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [AsyncBase クラス](../windows/asyncbase-class.md)