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
ms.openlocfilehash: 995594ee48e6ca408e88d9ab14968d88b536d309
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403517"
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

*pActivatibleClassId*<br/>
ランタイム クラスの IID。

*ppIFactory*<br/>
指定されたランタイム クラスの IActivationFactory します。

*サーバー名*<br/>
現在のモジュールでクラス ファクトリのサブセットの名前。 使用されるサーバー名を指定、 [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md)マクロ、または指定**nullptr**を既定のサーバー名を取得します。

## <a name="return-value"></a>戻り値

成功した場合は s_ok を返します。GetActivationFactory によってそれ以外の場合、HRESULT が返されます。

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Module クラス](../windows/module-class.md)<br/>
[ActivatableClass マクロ](../windows/activatableclass-macros.md)