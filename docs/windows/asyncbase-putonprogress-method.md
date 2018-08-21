---
title: Asyncbase::putonprogress メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::PutOnProgress
dev_langs:
- C++
helpviewer_keywords:
- PutOnProgress method
ms.assetid: 1f5f180e-eb5a-4afe-ac16-69dbf36f0383
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a99eee63496632b8f0918ee888e6a824424b757d
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649891"
---
# <a name="asyncbaseputonprogress-method"></a>AsyncBase::PutOnProgress メソッド
進行状況イベント ハンドラーのアドレスを指定した値に設定します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
STDMETHOD(  
   PutOnProgress  
)(TProgress* progressHandler);  
```  
  
### <a name="parameters"></a>パラメーター  
 *progressHandler*  
 進行状況イベントのハンドラーが設定されているアドレスです。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は s_ok を返します。それ以外の場合、E_ILLEGAL_METHOD_CALL します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [AsyncBase クラス](../windows/asyncbase-class.md)