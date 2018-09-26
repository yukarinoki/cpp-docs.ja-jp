---
title: IsSame 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 09/21/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsSame
- internal/Microsoft::WRL::Details::IsSame::value
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::IsSame structure
- Microsoft::WRL::Details::IsSame::value constant
ms.assetid: 1eddbc3f-3cc5-434f-8495-e4477e1f868e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a6d1e22d52a2e618357357555a549437ae453abe
ms.sourcegitcommit: edb46b0239a0e616af4ec58906e12338c3e8d2c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "47169698"
---
# <a name="issame-structure"></a>IsSame 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template <
   typename T1,
   typename T2
>
struct IsSame;
template <
   typename T1
>
struct IsSame<T1, T1>;
```

### <a name="parameters"></a>パラメーター

*T1*<br/>
型。

*T2*<br/>
別の型。

## <a name="remarks"></a>Remarks

別のと同じ型を指定した 1 つかどうかがテストには、種類が指定されました。

## <a name="members"></a>メンバー

### <a name="public-constants"></a>パブリック定数

名前                    | 説明
----------------------- | --------------------------------------------------
[Issame::value](#value) | 1 つの型が別のと同じかどうかを示します。

## <a name="inheritance-hierarchy"></a>継承階層

`IsSame`

## <a name="requirements"></a>要件

**ヘッダー:** internal.h

**Namespace:** Microsoft::WRL::Details

## <a name="value"></a>Issame::value

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

```cpp
template <typename T1, typename T2>
struct IsSame
{
    static const bool value = false;
};

template <typename T1>
struct IsSame<T1, T1>
{
    static const bool value = true;
};
```

### <a name="remarks"></a>Remarks

1 つの型が別のと同じかどうかを示します。

`value` `true`テンプレート パラメーターでは、同じ場合、`false`テンプレート パラメーターが異なる場合。
