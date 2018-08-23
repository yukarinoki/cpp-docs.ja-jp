---
title: ActivationFactoryCallback 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::ActivationFactoryCallback
dev_langs:
- C++
helpviewer_keywords:
- ActivationFactoryCallback function
ms.assetid: dd40c79b-1273-4f2a-8c24-ae9926fb4fd9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7979dd21d68c5b1e2606573a5271fc8deafdfb07
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42604181"
---
# <a name="activationfactorycallback-function"></a>ActivationFactoryCallback 関数

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
inline HRESULT STDAPICALLTYPE ActivationFactoryCallback(
   HSTRING activationId,
   IActivationFactory **ppFactory
);
```

### <a name="parameters"></a>パラメーター

*activationId*  
ランタイム クラス名を指定する文字列へのハンドルします。

*ppFactory*  
ときにこの操作が完了すると、パラメーターに対応するアクティベーション ファクトリ*activationId*します。

## <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。 可能性の高いエラー Hresult CLASS_E_CLASSNOTAVAILABLE、E_INVALIDARG です。

## <a name="remarks"></a>Remarks

指定されたアクティブ化 ID のアクティベーション ファクトリを取得します。

Windows ランタイムでは、ランタイム クラス名で指定されたオブジェクトを要求するには、このコールバック関数を呼び出します。

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)