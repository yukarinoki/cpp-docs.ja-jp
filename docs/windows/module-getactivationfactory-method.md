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
ms.openlocfilehash: 0e87ea3b0e44732d4271385073c48fd92e1aa114
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42608928"
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