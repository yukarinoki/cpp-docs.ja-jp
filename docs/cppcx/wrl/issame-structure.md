---
title: IsSame 構造体
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsSame
- internal/Microsoft::WRL::Details::IsSame::value
helpviewer_keywords:
- Microsoft::WRL::Details::IsSame structure
- Microsoft::WRL::Details::IsSame::value constant
ms.assetid: 1eddbc3f-3cc5-434f-8495-e4477e1f868e
ms.openlocfilehash: 8c209d5a8d2a35f2643e90e5595d86f41519f30b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216558"
---
# <a name="issame-structure"></a>IsSame 構造体

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template <typename T1, typename T2>
struct IsSame;

template <typename T1>
struct IsSame<T1, T1>;
```

### <a name="parameters"></a>パラメーター

*T1*<br/>
型。

*T2*<br/>
別の型。

## <a name="remarks"></a>解説

指定した1つの型が、指定した別の型と同じかどうかをテストします。

## <a name="members"></a>メンバー

### <a name="public-constants"></a>パブリック定数

名前                    | 説明
----------------------- | --------------------------------------------------
[IsSame:: 値](#value) | 一方の型が別の型と同じかどうかを示します。

## <a name="inheritance-hierarchy"></a>継承階層

`IsSame`

## <a name="requirements"></a>必要条件

**ヘッダー:** 内部 .h

**名前空間:** Microsoft:: WRL::D etails

## <a name="issamevalue"></a><a name="value"></a>IsSame:: 値

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

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

### <a name="remarks"></a>解説

一方の型が別の型と同じかどうかを示します。

`value`**`true`** テンプレートパラメーターが同じである場合は、 **`false`** テンプレートパラメーターが異なる場合はです。
