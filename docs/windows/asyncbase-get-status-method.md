---
title: Asyncbase::get_status メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::get_Status
dev_langs:
- C++
helpviewer_keywords:
- get_Status method
ms.assetid: 9823ecb9-212e-471d-b76f-7b8f21208905
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1590d07a7b37e7dd3abf09377a03734299cb124c
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39460959"
---
# <a name="asyncbasegetstatus-method"></a>AsyncBase::get_Status メソッド
非同期操作の状態を示す値を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHOD(  
   get_Status  
)(AsyncStatus *status) override;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *status*  
 状態が格納される場所です。 詳細については、Windows::Foundation::AsyncStatus 列挙型を参照してください。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は s_ok を返します。それ以外の場合、E_ILLEGAL_METHOD_CALL します。  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、`IAsyncInfo::get_Status` を実装します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [AsyncBase クラス](../windows/asyncbase-class.md)