---
title: _endthread、_endthreadex | Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _endthread
- _endthreadex
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
- _endthread
- endthreadex
- _endthreadex
- endthread
dev_langs:
- C++
helpviewer_keywords:
- _endthread function
- endthread function
- terminating threads
- endthreadex function
- _endthreadex function
- threading [C++], terminating threads
ms.assetid: 18a91f2f-659e-40b4-b266-ec12dcf2abf5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2bed0b93b2c9643a19aa8fd97c0e52da2ba1f8be
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43198791"
---
# <a name="endthread-endthreadex"></a>_endthread、_endthreadex

スレッドを終了します。**_endthread**によって作成されるスレッドを終了させる **_beginthread**と **_endthreadex**によって作成されるスレッドを終了させる **_beginthreadex**.

## <a name="syntax"></a>構文

```C
void _endthread( void );
void _endthreadex(
   unsigned retval
);
```

### <a name="parameters"></a>パラメーター

*retval*スレッドの終了コード。

## <a name="remarks"></a>Remarks

呼び出すことができます **_endthread**または **_endthreadex**明示的にスレッドを終了しますただし、 **_endthread**または **_endthreadex**が呼び出されます。パラメーターとして渡されたルーチンからスレッドが戻るときに自動的に **_beginthread**または **_beginthreadex**します。 呼び出しのスレッドを終了**endthread**または **_endthreadex**確実にスレッドに割り当てられたリソースの解放できます。

> [!NOTE]
> Libcmt.lib にリンクする実行可能ファイルでは、Win32 の [ExitThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-exitthread) API を呼び出さないでください。呼び出すと、割り当てられたリソースをランタイム システムで再利用することができなくなります。 **_endthread**と **_endthreadex**割り当てられているスレッド リソースを解放し、呼び出す**ExitThread**します。

**_endthread**スレッド ハンドルを自動的に終了します。 (この動作は、Win32 **ExitThread** API です)。したがって、使用 **_beginthread**と **_endthread**、Win32 を呼び出すことによって明示的にスレッド ハンドルを終了しないでください[CloseHandle](https://msdn.microsoft.com/library/windows/desktop/ms724211.aspx) API。

などの Win32 **ExitThread** API、 **_endthreadex**スレッド ハンドルを終了できません。 したがって、使用 **_beginthreadex**と **_endthreadex**、Win32 を呼び出してスレッド ハンドルを閉じる必要があります**CloseHandle** API。

> [!NOTE]
> **_endthread**と **_endthreadex**により呼び出されないスレッドで保留中の C++ デストラクター。

## <a name="requirements"></a>要件

|関数|必須ヘッダー|
|--------------|---------------------|
|**_endthread**|\<process.h>|
|**_endthreadex**|\<process.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md) のマルチスレッド バージョンのみ。

## <a name="example"></a>例

[_beginthread](beginthread-beginthreadex.md) の例を参照してください。

## <a name="see-also"></a>関連項目

[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[_beginthread、_beginthreadex](beginthread-beginthreadex.md)<br/>
