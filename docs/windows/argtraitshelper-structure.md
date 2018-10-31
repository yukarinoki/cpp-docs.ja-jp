---
title: ArgTraitsHelper 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 09/21/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraitsHelper
- event/Microsoft::WRL::Details::ArgTraitsHelper::args
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::ArgTraitsHelper structure
- Microsoft::WRL::Details::ArgTraitsHelper::args constant
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b608f5da893019d7700891968dcdc06489c563ea
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234230"
---
# <a name="argtraitshelper-structure"></a>ArgTraitsHelper 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template<typename TDelegateInterface>
struct ArgTraitsHelper;
```

### <a name="parameters"></a>パラメーター

*TDelegateInterface*<br/>
デリゲートのインターフェイスです。

## <a name="remarks"></a>Remarks

定義のデリゲート引数の一般的な特性に役立ちます。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前         | 説明
------------ | ------------------------------------------------------
`methodType` | `decltype(&TDelegateInterface::Invoke)` と同義。
`Traits`     | `ArgTraits<methodType>` と同義。

### <a name="public-constants"></a>パブリック定数

名前                           | 説明
------------------------------ | ---------------------------------------------------------------------------------------------------------------------
[Argtraitshelper::args](#args) | により、 [argtraits::args](#args)パラメーターの数のカウントを保持、`Invoke`デリゲート インターフェイスのメソッド。

## <a name="inheritance-hierarchy"></a>継承階層

`ArgTraitsHelper`

## <a name="requirements"></a>要件

**ヘッダー:** event.h

**Namespace:** Microsoft::WRL::Details

## <a name="args"></a>Argtraitshelper::args

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

```cpp
static const int args = Traits::args;
```

### <a name="remarks"></a>Remarks

により、`ArgTraitsHelper::args`パラメーターの数のカウントを保持、`Invoke`デリゲート インターフェイスのメソッド。
