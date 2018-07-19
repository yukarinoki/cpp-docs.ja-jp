---
title: _onexit、_onexit_m | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- onexit function
- registry, registering exit routines
- _onexit_m function
- onexit_m function
- _onexit function
- registering exit routines
- registering to be called on exit
ms.assetid: 45743298-0e2f-46cf-966d-1ca44babb443
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c190ce2c78135625a502d7509e56771fd670aa3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32401709"
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

**_onexit**正常終了した場合、関数へのポインターを返しますまたは**NULL**関数ポインターを格納する領域がない場合。

## <a name="remarks"></a>コメント

**_Onexit**関数には、関数のアドレスが渡されます (*関数*) プログラムが正常に終了したときに呼び出されます。 連続して呼び出す **_onexit** LIFO (最後に、先出し) の順序で実行される関数の登録を作成します。 渡される関数は、 **_onexit**パラメーターを受け取ることはできません。

場合と **_onexit**ルーチンに登録されている、DLL 内から呼び出さ **_onexit** DLL の実行の後にアンロードする**DllMain**がありますで呼び出されます。

**_onexit**は Microsoft 拡張機能です。 ANSI の移植性のためには、[atexit](atexit.md) を使用します。 **_Onexit_m**関数のバージョンは、混在モードの使用。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
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
