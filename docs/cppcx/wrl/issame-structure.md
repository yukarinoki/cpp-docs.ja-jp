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
ms.openlocfilehash: fcaf33309521b44163022e0ffa9b1e03e53e2551
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371340"
---
# <a name="issame-structure"></a>IsSame 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

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
別のタイプ。

## <a name="remarks"></a>解説

指定した型が、別の指定した型と同じであるかどうかをテストします。

## <a name="members"></a>メンバー

### <a name="public-constants"></a>パブリック定数

名前                    | 説明
----------------------- | --------------------------------------------------
[イサマ::値](#value) | ある型が別の型と同じであるかどうかを示します。

## <a name="inheritance-hierarchy"></a>継承階層

`IsSame`

## <a name="requirements"></a>必要条件

**ヘッダー:** 内部.h

**名前空間:** マイクロソフト::WRL::Dのテール

## <a name="issamevalue"></a><a name="value"></a>イサマ::値

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

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

ある型が別の型と同じであるかどうかを示します。

`value`は、テンプレートパラメータが同じ場合は**true、** テンプレートパラメータが異なる場合は**false**です。
