---
title: __setusermatherr | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
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
dev_langs:
- C++
helpviewer_keywords:
- __setusermatherr
ms.assetid: f306818d-381a-4d68-8739-71b92bacb5ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5c118cc5537690e8978ed2fd96b7727054ce5920
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101503"
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