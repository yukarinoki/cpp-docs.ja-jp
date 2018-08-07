---
title: Runtimeclass::addref メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::AddRef
dev_langs:
- C++
helpviewer_keywords:
- AddRef method
ms.assetid: 9c705749-680b-4308-bbec-5b601e8e7dbd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d7bd721d8f1edeedacc04515eef917899ed0c667
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608483"
---
# <a name="runtimeclassaddref-method"></a>RuntimeClass::AddRef メソッド
現在の参照カウントをインクリメント**RuntimeClass**オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHOD_(  
   ULONG,  
   AddRef  
)();  
```  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [RuntimeClass クラス](../windows/runtimeclass-class.md)