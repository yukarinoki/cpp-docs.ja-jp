---
description: '詳細情報: IsBaseOfStrict 構造体'
title: IsBaseOfStrict 構造体
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsBaseOfStrict
- internal/Microsoft::WRL::Details::IsBaseOfStrict::value
helpviewer_keywords:
- Microsoft::WRL::Details::IsBaseOfStrict structure
- Microsoft::WRL::Details::IsBaseOfStrict::value constant
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
ms.openlocfilehash: bcdab9c4b6b5a2ab108b59d3127c08b53589e16a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298956"
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict 構造体

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template <typename Base, typename Derived>
struct IsBaseOfStrict;

template <typename Base>
struct IsBaseOfStrict<Base, Base>;
```

### <a name="parameters"></a>パラメーター

*常用*<br/>
基本データ型。

*派生*<br/>
派生型。

## <a name="remarks"></a>解説

一方の型がもう一方の型の基本クラスであるかどうかをテストします。

1つ目のテンプレートでは、型が基本型から派生しているかどうかをテストします。この場合、またはが発生する可能性があり **`true`** **`false`** ます。 2番目のテンプレートは、型がそれ自体から派生しているかどうかをテストします。これは常にを生成 **`false`** します。

## <a name="members"></a>メンバー

### <a name="public-constants"></a>パブリック定数

名前                            | 説明
------------------------------- | --------------------------------------------------
[IsBaseOfStrict:: value](#value) | 一方の型が別の型のベースであるかどうかを示します。

## <a name="inheritance-hierarchy"></a>継承階層

`IsBaseOfStrict`

## <a name="requirements"></a>要件

**ヘッダー:** 内部 .h

**名前空間:** Microsoft:: WRL::D etails

## <a name="isbaseofstrictvalue"></a><a name="value"></a> IsBaseOfStrict:: value

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
static const bool value = __is_base_of(Base, Derived);
```

### <a name="remarks"></a>解説

一方の型が別の型のベースであるかどうかを示します。

`value`**`true`** 型 `Base` が型の基底クラスである場合は `Derived` 、それ以外の場合はです **`false`** 。
