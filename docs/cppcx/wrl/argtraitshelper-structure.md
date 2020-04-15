---
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
ms.openlocfilehash: 4acbd9fa660f29bbaf209282ff0e90f43621574d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360779"
---
# <a name="argtraitshelper-structure"></a>ArgTraitsHelper 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template<typename TDelegateInterface>
struct ArgTraitsHelper;
```

### <a name="parameters"></a>パラメーター

*インターフェイス*<br/>
デリゲート インターフェイス。

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
[アルストレイトヘルパー::args](#args) | [ArgTraits::args は](#args)、デリゲート インターフェイスのメソッドのパラメーター`Invoke`数を保持するのに役立ちます。

## <a name="inheritance-hierarchy"></a>継承階層

`ArgTraitsHelper`

## <a name="requirements"></a>必要条件

**ヘッダー:** イベント.h

**名前空間:** マイクロソフト::WRL::Dのテール

## <a name="argtraitshelperargs"></a><a name="args"></a>アルストレイトヘルパー::args

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
static const int args = Traits::args;
```

### <a name="remarks"></a>解説

デリゲート`ArgTraitsHelper::args`インターフェイスのメソッドのパラメーター数を`Invoke`保持するのに役立ちます。
