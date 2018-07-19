---
title: quick_exit1 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- quick_exit
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
- quick_exit
- process/quick_exit
- stdlib/quick_exit
dev_langs:
- C++
helpviewer_keywords:
- quick_exit function
ms.assetid: ecfbdae6-01c4-45fa-aaeb-b368e1de2a9c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de3eb88093db0eea470a0c1d775516574c466ddd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405732"
---
# <a name="quickexit"></a>quick_exit

通常のプログラムが終了するようにします。

## <a name="syntax"></a>構文

```C
__declspec(noreturn) void quick_exit(
    int status
);
```

### <a name="parameters"></a>パラメーター

*status*<br/>
ホスト環境に戻るためのステータス コード。

## <a name="return-value"></a>戻り値

**Quick_exit**関数は、呼び出し元に返すことはできません。

## <a name="remarks"></a>コメント

**Quick_exit**関数は、通常のプログラムが終了します。 によって登録された関数が呼び出すない**atexit**、 **_onexit**またはシグナル ハンドラーによって登録されている、**信号**関数。 ときの動作は定義されている**quick_exit**に 1 回以上、または場合に呼び出されますが、**終了**関数とも呼びます。

**Quick_exit**関数後入れ先出し (LIFO) の順序、によって登録された関数の呼び出し**at_quick_exit**を除き、関数が登録されている関数が既にときに呼び出されます。  [longjmp](longjmp.md) 呼び出しが、関数の呼び出しを終了する登録済み関数を呼び出している間に呼び出される場合、動作は定義されません。

登録済みの関数が呼び出された後**quick_exit**呼び出します **_Exit**を使用して、*ステータス*にコントロールをホスト環境に返す値。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**quick_exit**|\<process.h> または \<stdlib.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec、_wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit、_Exit、_exit](exit-exit-exit.md)<br/>
[_onexit、_onexit_m](onexit-onexit-m.md)<br/>
[_spawn 系関数と _wspawn 系関数](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system、_wsystem](system-wsystem.md)<br/>
