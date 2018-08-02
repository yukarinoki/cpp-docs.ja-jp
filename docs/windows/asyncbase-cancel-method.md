---
title: Asyncbase::cancel メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Cancel
dev_langs:
- C++
helpviewer_keywords:
- Cancel method
ms.assetid: 8bfebc63-3848-4629-bc89-aa538ed7e7ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ee338d4e90f94ed7cb7f9158235c66b72e9f2e52
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464747"
---
# <a name="asyncbasecancel-method"></a>AsyncBase::Cancel メソッド
非同期操作をキャンセルします。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHOD(  
   Cancel  
)(void);  
```  
  
## <a name="return-value"></a>戻り値  
 既定では、常に S_OK を返します。  
  
## <a name="remarks"></a>Remarks  
 `Cancel()` 既定の実装は、 `IAsyncInfo::Cancel`、実際の作業を行いません。 実際には、非同期操作をキャンセルするには、オーバーライド、`OnCancel()`純粋仮想メソッド。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [AsyncBase クラス](../windows/asyncbase-class.md)