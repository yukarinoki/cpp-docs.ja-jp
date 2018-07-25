---
title: Module::getactivationfactory メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GetActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- GetActivationFactory method
ms.assetid: 59da8844-072e-414b-b89c-1db1cc4fd81d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 837cb68173ca1994de6bc560882d617bb3aa03e0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33887014"
---
# <a name="modulegetactivationfactory-method"></a>Module::GetActivationFactory メソッド
モジュールのアクティベーション ファクトリを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
WRL_NOTHROW HRESULT GetActivationFactory(  
   _In_ HSTRING pActivatibleClassId,  
   _Deref_out_ IActivationFactory **ppIFactory,  
   wchar_t* serverName = nullptr  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pActivatibleClassId`  
 ランタイム クラスの IID です。  
  
 `ppIFactory`  
 指定したランタイム クラスの IActivationFactory します。  
  
 `serverName`  
 現在のモジュールでクラス ファクトリのサブセットの名前。 使用されるサーバー名を指定、 [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md)マクロ、または指定`nullptr`を既定のサーバー名を取得します。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は S_OK、GetActivationFactory によって返された HRESULT のそれ以外の場合。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
[モジュール クラス](../windows/module-class.md) [ActivatableClass マクロ](../windows/activatableclass-macros.md)