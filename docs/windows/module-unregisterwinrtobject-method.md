---
title: Module::unregisterwinrtobject メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::UnregisterWinRTObject
dev_langs:
- C++
helpviewer_keywords:
- UnregisterWinRTObject method
ms.assetid: 32334aa7-2293-40d2-9a89-4b02e2e31f3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 93c804f9e7701ab3bf021902b62ae3f1b414d61c
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40019080"
---
# <a name="moduleunregisterwinrtobject-method"></a>Module::UnregisterWinRTObject メソッド
他のアプリケーションがそれらに接続できないように、1 つまたは複数の Windows ランタイム オブジェクトを登録解除します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
virtual HRESULT UnregisterWinRTObject(  
   unsigned int,  
   _Inout_ WINRT_REGISTRATION_COOKIE* cookie  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 *Cookie*  
 登録を取り消すことは、クラス オブジェクトを識別する値へのポインター。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>関連項目
 [Module クラス](../windows/module-class.md)