---
description: '詳細については、次を参照してください: ArgTraitsHelper 構造体'
title: ArgTraitsHelper 構造体
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraitsHelper
- event/Microsoft::WRL::Details::ArgTraitsHelper::args
helpviewer_keywords:
- Microsoft::WRL::Details::ArgTraitsHelper structure
- Microsoft::WRL::Details::ArgTraitsHelper::args constant
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
ms.openlocfilehash: a749c48c72c837eb0898d32ddd08410b87918871
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175860"
---
# <a name="argtraitshelper-structure"></a>ArgTraitsHelper 構造体

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template<typename TDelegateInterface>
struct ArgTraitsHelper;
```

### <a name="parameters"></a>パラメーター

*TDelegateInterface*<br/>
デリゲートインターフェイス。

## <a name="remarks"></a>解説

デリゲート引数の共通の特性を定義するのに役立ちます。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前         | 説明
------------ | ------------------------------------------------------
`methodType` | `decltype(&TDelegateInterface::Invoke)` と同義。
`Traits`     | `ArgTraits<methodType>` と同義。

### <a name="public-constants"></a>パブリック定数

名前                           | 説明
------------------------------ | ---------------------------------------------------------------------------------------------------------------------
[ArgTraitsHelper:: args](#args) | [Argtraits:: args](#args)は、 `Invoke` デリゲートインターフェイスのメソッドのパラメーター数を保持するのに役立ちます。

## <a name="inheritance-hierarchy"></a>継承階層

`ArgTraitsHelper`

## <a name="requirements"></a>要件

**ヘッダー:** イベント .h

**名前空間:** Microsoft:: WRL::D etails

## <a name="argtraitshelperargs"></a><a name="args"></a> ArgTraitsHelper:: args

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
static const int args = Traits::args;
```

### <a name="remarks"></a>解説

`ArgTraitsHelper::args`デリゲートインターフェイスのメソッドのパラメーター数を保持するのに役立ち `Invoke` ます。
