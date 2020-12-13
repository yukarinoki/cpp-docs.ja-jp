---
description: '詳細については、次を参照してください: quick_exit'
title: quick_exit1
ms.date: 11/04/2016
api_name:
- quick_exit
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- quick_exit
- process/quick_exit
- stdlib/quick_exit
helpviewer_keywords:
- quick_exit function
ms.assetid: ecfbdae6-01c4-45fa-aaeb-b368e1de2a9c
ms.openlocfilehash: 85640af902092d5cc60a1c718dfd8999c41406b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137099"
---
# <a name="quick_exit"></a>quick_exit

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

**Quick_exit** 関数は、呼び出し元に戻ることができません。

## <a name="remarks"></a>解説

**Quick_exit** 関数により、通常のプログラムの終了が発生します。 このメソッドは、 **atexit**、 **_onexit** 、または **シグナル関数に** よって登録されたシグナルハンドラーによって登録された関数を呼び出しません。 **Quick_exit** が複数回呼び出される場合、または **exit** 関数も呼び出される場合、動作は定義されません。

**Quick_exit** 関数は、 **at_quick_exit** によって登録された関数を、後入れ先出し (LIFO) の順序で呼び出します。ただし、関数の登録時に既に呼び出されている関数は除きます。  [longjmp](longjmp.md) 呼び出しが、関数の呼び出しを終了する登録済み関数を呼び出している間に呼び出される場合、動作は定義されません。

登録されている関数が呼び出されると、 **quick_exit** は、 *status* 値を使用してホスト環境に制御を返すことで **_Exit** を呼び出します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**quick_exit**|\<process.h> または \<stdlib.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[プロセスと環境の制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[取り消し](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec, _wexec 関数](../../c-runtime-library/exec-wexec-functions.md)<br/>
[終了、_Exit、_exit](exit-exit-exit.md)<br/>
[_onexit、_onexit_m](onexit-onexit-m.md)<br/>
[_spawn, _wspawn 関数](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system、_wsystem](system-wsystem.md)<br/>
