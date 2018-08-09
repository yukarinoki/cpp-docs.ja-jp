---
title: Module::unregisterobjects メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::UnregisterObjects
dev_langs:
- C++
helpviewer_keywords:
- UnregisterObjects method
ms.assetid: 3d8119a7-991d-45e9-b8c5-ed36c0be0332
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c46fad71a42f9f947f020709cdf7851d079edd81
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014027"
---
# <a name="moduleunregisterobjects-method"></a>Module::UnregisterObjects メソッド
他のアプリケーションがそれらに接続できないように、指定したモジュール内のオブジェクトを登録解除します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT UnregisterObjects(  
   ModuleBase* module,  
   const wchar_t* serverName);  
```  
  
### <a name="parameters"></a>パラメーター  
 *モジュール*  
 モジュールへのポインター。  
  
 *サーバー名*  
 この操作によって影響を受けるオブジェクトのサブセットを指定する修飾名。  
  
## <a name="return-value"></a>戻り値  
 この操作が成功した場合は s_ok を返します。それ以外の場合、エラー理由を示す HRESULT がこの操作に失敗しました。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>関連項目
 [Module クラス](../windows/module-class.md)