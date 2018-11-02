---
title: GetActivationFactory 関数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::GetActivationFactory
- client/ABI::Windows::Foundation::GetActivationFactory
- client/Windows::Foundation::GetActivationFactory
helpviewer_keywords:
- GetActivationFactory function
ms.assetid: 5736d285-6beb-42aa-8788-e261c0010afe
ms.openlocfilehash: a2581fce3c15c96317bf68de0ed918b19edd8b38
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481709"
---
# <a name="getactivationfactory-function"></a>GetActivationFactory 関数

テンプレート パラメーターで指定された型のアクティベーション ファクトリを取得します。

## <a name="syntax"></a>構文

```cpp
template<typename T>
inline HRESULT GetActivationFactory(
   _In_ HSTRING activatableClassId,
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> factory
);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
アクティベーション ファクトリの種類を指定するテンプレート パラメーター。

*activatableClassId*<br/>
アクティベーション ファクトリを作成できるクラスの名前。

*ファクトリ*<br/>
ときにこの操作が完了すると、型のアクティベーション ファクトリへの参照を*T*します。

## <a name="return-value"></a>戻り値

成功した場合は s_ok を返します。それ以外の場合、この操作が失敗した理由を示す HRESULT エラー。

## <a name="requirements"></a>必要条件

**ヘッダー:** client.h

**Namespace:** windows::foundation

## <a name="see-also"></a>関連項目

[Windows::Foundation 名前空間](../windows/windows-foundation-namespace.md)