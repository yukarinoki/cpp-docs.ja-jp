---
description: '詳細については、次を参照してください: __RTDynamicCast'
title: __RTDynamicCast
ms.date: 1/14/2021
api_name:
- __RTDynamicCast
api_location:
- msvcr90.dll
- msvcr110.dll
- msvcr120.dll
- msvcrt.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __RTDynamicCast
helpviewer_keywords:
- __RTDynamicCast
ms.assetid: 56aa2d7a-aa47-46ef-830d-e37175611239
ms.openlocfilehash: cefd5248e0409b72f97c959d08aa30b1c0167e26
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "98243113"
---
# <a name="__rtdynamiccast"></a>__RTDynamicCast

[dynamic_cast](../cpp/dynamic-cast-operator.md) 演算子のランタイム実装です。

## <a name="syntax"></a>構文

```cpp
PVOID __RTDynamicCast (
   PVOID inptr,
   LONG VfDelta,
   PVOID SrcType,
   PVOID TargetType,
   BOOL isReference
   ) throw(...)
```

#### <a name="parameters"></a>パラメーター

*inptr*<br/>
ポリモーフィック型オブジェクトへのポインター。

*VfDelta*<br/>
オブジェクト内の仮想関数ポインターのオフセット。

*Desttype*<br/>
`inptr` パラメーターでポイントするオブジェクトのスタティック型。

*TargetType*<br/>
キャストの意図した結果。

*isReference*<br/>
**`true`** 入力が参照である場合は。 **`false`** 入力がポインターである場合は。

## <a name="return-value"></a>戻り値

成功した場合は、適切なサブオブジェクトへのポインター。それ以外の場合は **NULL**。

## <a name="exceptions"></a>例外

`dynamic_cast<>` への入力が参照でありキャストに失敗した場合は `bad_cast()`。

## <a name="remarks"></a>注釈

`inptr` を `TargetType` 型のオブジェクトに変換します。 `inptr` の型は、`TargetType` がポインターの場合はポインター、`TargetType` が参照の場合は左辺値である必要があります。 `TargetType` は、以前に定義されたクラス型への参照かポインター、または void 型へのポインターである必要があります。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|__RTDynamicCast|rtti.h|
