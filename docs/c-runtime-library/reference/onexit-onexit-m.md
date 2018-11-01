---
title: _onexit、_onexit_m
ms.date: 11/04/2016
apiname:
- _onexit
- _onexit_m
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
apitype: DLLExport
f1_keywords:
- _onexit
- onexit_m
- onexit
- _onexit_m
helpviewer_keywords:
- onexit function
- registry, registering exit routines
- _onexit_m function
- onexit_m function
- _onexit function
- registering exit routines
- registering to be called on exit
ms.assetid: 45743298-0e2f-46cf-966d-1ca44babb443
ms.openlocfilehash: c190f777032904802f771bab9fc323ba305ff32e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50609606"
---
# <a name="onexit-onexitm"></a>_onexit、_onexit_m

終了時に呼び出されるルーチンを登録します。

## <a name="syntax"></a>構文

```C
_onexit_t _onexit(
   _onexit_t function
);
_onexit_t_m _onexit_m(
   _onexit_t_m function
);
```

### <a name="parameters"></a>パラメーター

*function*<br/>
終了時に呼び出される関数へのポインター。

## <a name="return-value"></a>戻り値

**_onexit**成功した場合、関数へのポインターを返しますまたは**NULL**関数ポインターを格納する領域がない場合。

## <a name="remarks"></a>Remarks

**_Onexit**関数には、関数のアドレスが渡されます (*関数*) プログラムが正常に終了したときに呼び出されます。 連続して呼び出す **_onexit** LIFO (最後に、最初に取り出さ) の順序で実行される関数のレジスタが作成されます。 渡される関数は、 **_onexit**パラメーターを受け取ることはできません。

場合と **_onexit**で登録されたルーチン、DLL 内から呼び出される **_onexit** DLL の実行の後にアンロードする**DllMain**が DLL_PROCESS_DETACH で呼び出されます。

**_onexit**は Microsoft 拡張機能です。 ANSI の移植性のためには、[atexit](atexit.md) を使用します。 **_Onexit_m**関数のバージョンは、混在モードを使用します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_onexit**|\<stdlib.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_onexit.c

#include <stdlib.h>
#include <stdio.h>

/* Prototypes */
int fn1(void), fn2(void), fn3(void), fn4 (void);

int main( void )
{
   _onexit( fn1 );
   _onexit( fn2 );
   _onexit( fn3 );
   _onexit( fn4 );
   printf( "This is executed first.\n" );
}

int fn1()
{
   printf( "next.\n" );
   return 0;
}

int fn2()
{
   printf( "executed " );
   return 0;
}

int fn3()
{
   printf( "is " );
   return 0;
}

int fn4()
{
   printf( "This " );
   return 0;
}
```

### <a name="output"></a>出力

```Output
This is executed first.
This is executed next.
```

## <a name="see-also"></a>関連項目

[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[atexit](atexit.md)<br/>
[exit、_Exit、_exit](exit-exit-exit.md)<br/>
[__dllonexit](../../c-runtime-library/dllonexit.md)<br/>
