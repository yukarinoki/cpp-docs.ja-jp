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
ms.openlocfilehash: 4384d67060d2f5d992c098841f76a6b858b78c15
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
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
 `pf`  
 ユーザーによって提供された `_matherr` の実装へのポインター。  
  
 `pf` パラメーターの型は `typedef int (__cdecl * _HANDLE_MATH_ERROR)(struct _exception *)` として宣言されます。  
  
## <a name="remarks"></a>コメント  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|__setusermatherr|matherr.c|