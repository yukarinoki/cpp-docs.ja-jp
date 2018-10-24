---
title: _lock | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _lock
apilocation:
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- msvcr90.dll
- msvcr80.dll
- msvcr110.dll
- msvcrt.dll
- msvcr120_clr0400.dll
apitype: DLLExport
f1_keywords:
- lock
- _lock
dev_langs:
- C++
helpviewer_keywords:
- lock function
- _lock function
ms.assetid: 29f77c37-30de-4b3d-91b6-030216e645a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 38cd49dd483b556c8bda95e7a77109a9d4682e7c
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2018
ms.locfileid: "48233620"
---
# <a name="lock"></a>_lock

マルチスレッドのロックを取得します。

> [!IMPORTANT]
>  これは古い関数です。 Visual Studio 2015 以降、CRT で使用できません。

## <a name="syntax"></a>構文

```
void __cdecl _lock
   int locknum
);
```

#### <a name="parameters"></a>パラメーター

*locknum*<br/>
[in] 取得するロックの識別子。

## <a name="remarks"></a>コメント

ロックが既に取得されている場合は、このメソッドによってあらためてロックが取得され、内部 C ランタイム (CRT) エラーが発生します。 メソッドでロックを取得できない場合は、致命的なエラーで終了し、エラー コードが `_RT_LOCK`に設定されます。

## <a name="requirements"></a>必要条件

**ソース:** mlock.c

## <a name="see-also"></a>参照

[関数リファレンス (アルファベット順)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[_unlock](../c-runtime-library/unlock.md)