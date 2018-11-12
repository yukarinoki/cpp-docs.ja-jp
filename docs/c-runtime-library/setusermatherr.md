---
title: __setusermatherr
ms.date: 11/04/2016
apiname:
- __setusermatherr
apilocation:
- msvcr80.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __setusermatherr
helpviewer_keywords:
- __setusermatherr
ms.assetid: f306818d-381a-4d68-8739-71b92bacb5ea
ms.openlocfilehash: 116abd203cc289c63535a8e41a005a6fd248b08b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50640467"
---
# <a name="setusermatherr"></a>__setusermatherr

数値演算エラーを処理するために、[_matherr](../c-runtime-library/reference/matherr.md) ルーチンではなく、ユーザーが指定したルーチンを指定します。

## <a name="syntax"></a>構文

```cpp
void __setusermatherr(
   _HANDLE_MATH_ERROR pf
   )
```

#### <a name="parameters"></a>パラメーター

*/pf*<br/>
ユーザーによって提供された `_matherr` の実装へのポインター。

*pf* パラメーターの型は `typedef int (__cdecl * _HANDLE_MATH_ERROR)(struct _exception *)` として宣言されます。

## <a name="remarks"></a>コメント

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|__setusermatherr|matherr.c|