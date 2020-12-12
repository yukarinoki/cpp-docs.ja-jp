---
description: '詳細情報: GetActivationFactory 関数'
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
ms.openlocfilehash: ae2384e0620282723c6f10090a0028347408b271
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124632"
---
# <a name="getactivationfactory-function"></a>GetActivationFactory 関数

テンプレートパラメーターによって指定された型のアクティベーションファクトリを取得します。

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
アクティベーションファクトリの型を指定するテンプレートパラメーター。

*activatableClassId*<br/>
アクティベーションファクトリが生成できるクラスの名前。

*factory*<br/>
この操作が完了すると、 *T* 型のアクティベーションファクトリへの参照。

## <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、この操作が失敗した理由を示すエラー HRESULT。

## <a name="requirements"></a>要件

**ヘッダー:** client.h

**名前空間:** Windows:: Foundation

## <a name="see-also"></a>関連項目

[Windows:: Foundation 名前空間](windows-foundation-namespace.md)
