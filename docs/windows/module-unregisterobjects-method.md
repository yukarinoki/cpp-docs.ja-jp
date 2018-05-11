---
title: Module::unregisterobjects メソッド |Microsoft ドキュメント
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
ms.openlocfilehash: 7b711338c436eda3e64d9b51ef0d3137975d834a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="moduleunregisterobjects-method"></a>Module::UnregisterObjects メソッド
指定したモジュール内のオブジェクトの登録を解除して、他のアプリケーションがそれらに接続できないようにします。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT UnregisterObjects(  
   ModuleBase* module,  
   const wchar_t* serverName);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `module`  
 モジュールへのポインター。  
  
 `serverName`  
 この操作によって影響を受けるオブジェクトのサブセットを指定する修飾名。  
  
## <a name="return-value"></a>戻り値  
 この操作が成功した場合は S_OK、それ以外の場合、エラーの理由を示す hresult 値この操作に失敗しました。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>関連項目
 [Module クラス](../windows/module-class.md)