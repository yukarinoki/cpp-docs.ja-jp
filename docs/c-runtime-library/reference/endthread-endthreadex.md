---
title: _endthread、_endthreadex
ms.date: 4/2/2020
api_name:
- _endthread
- _endthreadex
- _o__endthread
- _o__endthreadex
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _endthread
- endthreadex
- _endthreadex
- endthread
helpviewer_keywords:
- _endthread function
- endthread function
- terminating threads
- endthreadex function
- _endthreadex function
- threading [C++], terminating threads
ms.assetid: 18a91f2f-659e-40b4-b266-ec12dcf2abf5
ms.openlocfilehash: c76f479255080400e07678ef5dbde572b7a9dffc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348037"
---
# <a name="_endthread-_endthreadex"></a>_endthread、_endthreadex

スレッドを終了します。**_endthread**は **、_beginthread**によって作成されたスレッドを終了し **、_beginthreadex****によって作成**されたスレッドを終了_endthreadex。

## <a name="syntax"></a>構文

```C
void _endthread( void );
void _endthreadex(
   unsigned retval
);
```

### <a name="parameters"></a>パラメーター

*retval*<br/>
スレッド終了コード。

## <a name="remarks"></a>解説

**_endthread**呼び出したり **、スレッドを終了_endthreadex**明示的に呼び出したりできます。ただし **、_endthread**または **_endthreadex**は、_beginthreadまたは **_beginthreadex**にパラメータとして渡されたルーチンからスレッドが戻 **_beginthread**ったときに自動的に呼び出されます。 **スレッドを終了**または **_endthreadex**呼び出しで終了すると、スレッドに割り当てられたリソースを適切に回復できます。

> [!NOTE]
> Libcmt.lib にリンクする実行可能ファイルでは、Win32 の [ExitThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitthread) API を呼び出さないでください。呼び出すと、割り当てられたリソースをランタイム システムで再利用することができなくなります。 **割**り当てられたスレッド リソース**を**_endthreadし、_endthreadexし **、ExitThread**を呼び出します。

**_endthread**は、スレッド ハンドルを自動的に閉じます。 (この動作は、Win32**の終了スレッド**API とは異なります。したがって **、_beginthread**を使用して **_endthread**場合は、Win32 [CloseHandle](/windows/win32/api/handleapi/nf-handleapi-closehandle) API を呼び出してスレッド ハンドルを明示的に閉じないでください。

Win32 **ExitThread** API と同様**に、_endthreadex**はスレッド ハンドルを閉じません。 したがって **、_beginthreadex**を使用して **_endthreadex**場合は、Win32 **CloseHandle** API を呼び出してスレッド ハンドルを閉じる必要があります。

> [!NOTE]
> **_endthread**と **_endthreadex、** スレッドで保留中の C++ デストラクターが呼び出されない原因となります。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|
|--------------|---------------------|
|**_endthread**|\<process.h>|
|**_endthreadex**|\<process.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md) のマルチスレッド バージョンのみ。

## <a name="example"></a>例

[_beginthread](beginthread-beginthreadex.md)の例を参照してください。

## <a name="see-also"></a>関連項目

[プロセスと環境の制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[_beginthread、_beginthreadex](beginthread-beginthreadex.md)<br/>
