---
title: Module::getactivationfactory メソッド |Microsoft Docs
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
ms.openlocfilehash: f6fda1c514b6cb3e60a55d35323bf8b116f850ac
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011869"
---
# <a name="modulegetactivationfactory-method"></a>Module::GetActivationFactory メソッド
モジュールのアクティベーション ファクトリを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
WRL_NOTHROW HRESULT GetActivationFactory(  
   _In_ HSTRING pActivatibleClassId,  
   _Deref_out_ IActivationFactory **ppIFactory,  
   wchar_t* serverName = nullptr  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 *pActivatibleClassId*  
 ランタイム クラスの IID。  
  
 *ppIFactory*  
 指定されたランタイム クラスの IActivationFactory します。  
  
 *サーバー名*  
 現在のモジュールでクラス ファクトリのサブセットの名前。 使用されるサーバー名を指定、 [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md)マクロ、または指定**nullptr**を既定のサーバー名を取得します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は s_ok を返します。GetActivationFactory によってそれ以外の場合、HRESULT が返されます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Module クラス](../windows/module-class.md)  
 [ActivatableClass マクロ](../windows/activatableclass-macros.md)