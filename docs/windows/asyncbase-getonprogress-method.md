---
title: Asyncbase::getonprogress メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::GetOnProgress
dev_langs:
- C++
helpviewer_keywords:
- GetOnProgress method
ms.assetid: 286ddc9c-3e30-41a2-8e8b-e53d3fb0649d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 83af39180da819349e95051c57dc137835db87bb
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="asyncbasegetonprogress-method"></a>AsyncBase::GetOnProgress メソッド
指定された変数に現在の進行状況イベント ハンドラーのアドレスをコピーします。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHOD(  
   GetOnProgress  
)(TProgress** progressHandler);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `progressHandler`  
 現在の進行状況イベント ハンドラーのアドレスが格納されている場所です。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は S_OK、それ以外の場合、E_ILLEGAL_METHOD_CALL です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [AsyncBase クラス](../windows/asyncbase-class.md)