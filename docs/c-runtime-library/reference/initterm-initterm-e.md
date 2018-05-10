---
title: _initterm、_initterm_e | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _initterm_e
- _initterm
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _initterm_e
- initterm
- _initterm
- initterm_e
dev_langs:
- C++
helpviewer_keywords:
- initterm function
- initterm_e function
- _initterm function
- _initterm_e function
ms.assetid: 85131efe-c747-429a-8897-bcdedb000172
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 470ad6cbf13efb170f61aa12f7859f2baa248c2b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="initterm-initterme"></a>_initterm, _initterm_e

関数ポインターのテーブルを調査して初期化する内部メソッドです。

1 番目のポインターにはテーブル内の開始位置を、2 番目のポインターには終了位置を指定します。

## <a name="syntax"></a>構文

```C
void __cdecl _initterm(
   PVFV *,
   PVFV *
);

int __cdecl _initterm_e(
   PVFV *,
   PVFV *
);
```

## <a name="return-value"></a>戻り値

初期化に失敗した場合は 0 以外のエラーコードが返され、エラーがスローされます。エラーが発生しなかった場合は 0 が返されます。

## <a name="remarks"></a>コメント

これらのメソッドは、C++ プログラムの初期化時にのみ内部的に呼び出されるものです。 プログラムでは呼び出さないでください。

これらのメソッドでは、関数のエントリのテーブルについて説明、ときにスキップ**NULL**エントリして続行します。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
