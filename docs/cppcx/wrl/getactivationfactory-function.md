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
ms.openlocfilehash: 3e138eee9e5bc02971cd1eb34c78f2be4ad5c9a0
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033944"
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

*factory*<br/>
ときにこの操作が完了すると、型のアクティベーション ファクトリへの参照を*T*します。

## <a name="return-value"></a>戻り値

成功した場合は s_ok を返します。それ以外の場合、この操作が失敗した理由を示す HRESULT エラー。

## <a name="requirements"></a>必要条件

**ヘッダー:** client.h

**名前空間:** Windows::Foundation

## <a name="see-also"></a>関連項目

[Windows::Foundation 名前空間](windows-foundation-namespace.md)