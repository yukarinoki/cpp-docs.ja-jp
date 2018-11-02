---
title: quick_exit1
ms.date: 11/04/2016
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
helpviewer_keywords:
- quick_exit function
ms.assetid: ecfbdae6-01c4-45fa-aaeb-b368e1de2a9c
ms.openlocfilehash: 50f1ee72cce04c2bebc8f7396a2b6fad98301dd7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429016"
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

**Quick_exit**関数の呼び出し元に戻すことはできません。

## <a name="remarks"></a>Remarks

**Quick_exit**関数は、通常のプログラムの終了。 によって登録された関数が呼び出すない**atexit**、 **_onexit**またはシグナル ハンドラーが登録されている、**信号**関数。 場合の動作は定義されません**quick_exit**に 1 回以上、または場合に呼び出されますが、**終了**関数ともいいます。

**Quick_exit**関数呼び出しの最後で、先入れ先出し (LIFO) 順、によって登録された関数で**at_quick_exit**関数が登録されたときに既に呼び出されている関数を除き、します。  [longjmp](longjmp.md) 呼び出しが、関数の呼び出しを終了する登録済み関数を呼び出している間に呼び出される場合、動作は定義されません。

登録済みの関数が呼び出された後**quick_exit**呼び出す **_Exit**を使用して、*状態*にコントロールをホスト環境に返される値。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
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
