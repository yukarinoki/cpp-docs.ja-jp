---
title: Asyncbase::close メソッド |Microsoft Docs
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
ms.openlocfilehash: 3ce391e95aa9e08ae7d99e3cbdf064721ce21dbe
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643538"
---
# <a name="asyncbaseclose-method"></a>AsyncBase::Close メソッド
非同期操作を閉じます。  
  
## <a name="syntax"></a>構文  
  
```cpp  
STDMETHOD(  
   Close  
)(void) override;  
```  
  
## <a name="return-value"></a>戻り値  
 操作を閉じるかまたは既に場合は S_OK が閉じられました。それ以外の場合、E_ILLEGAL_STATE_CHANGE します。  
  
## <a name="remarks"></a>Remarks  
 **Close()** の既定の実装は、 `IAsyncInfo::Close`、実際の作業を行いません。 実際に閉じる非同期操作には、オーバーライド、`OnClose()`純粋仮想メソッド。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [AsyncBase クラス](../windows/asyncbase-class.md)