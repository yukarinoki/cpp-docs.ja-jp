---
description: '詳細情報: atexit'
title: atexit
ms.date: 11/04/2016
api_name:
- atexit
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- atexit
helpviewer_keywords:
- processing, at exit
- atexit function
ms.assetid: 92c156d2-8052-4e58-96dc-00128baac6f9
ms.openlocfilehash: 82c0bbfdb9af62faff9239781b5db340183e25fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117537"
---
# <a name="atexit"></a>atexit

終了時に指定された関数を処理します。

## <a name="syntax"></a>構文

```C
int atexit(
   void (__cdecl *func )( void )
);
```

### <a name="parameters"></a>パラメーター

*func*<br/>
呼び出される関数。

## <a name="return-value"></a>戻り値

**atexit** は成功した場合は0、エラーが発生した場合は0以外の値を返します。

## <a name="remarks"></a>解説

**Atexit** 関数には、プログラムが正常に終了したときに呼び出される関数 *func* のアドレスが渡されます。 **Atexit** を連続して呼び出すと、後入れ先出し (LIFO) の順序で実行される関数のレジスタが作成されます。 **Atexit** に渡される関数は、パラメーターを受け取ることができません。 **atexit** および **_onexit** は、ヒープを使用して関数のレジスタを保持します。 したがって、登録可能な関数の数は、ヒープ メモリの量によってのみ制限されます。

**Atexit** 関数のコードには、 **atexit** 関数が呼び出されたときに既にアンロードされている可能性のある DLL に対する依存関係を含めることはできません。

ANSI 準拠のアプリケーションを生成するには、(類似の **_onexit** 関数ではなく) ansi 標準の **atexit** 関数を使用します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**atexit**|\<stdlib.h>|

## <a name="example"></a>例

このプログラムは、 **atexit** が呼び出されたときに実行される関数のスタックに4つの関数をプッシュします。 プログラムの終了時に、後入れ先出し法でこれらのプログラムが実行されます。

```C
// crt_atexit.c
#include <stdlib.h>
#include <stdio.h>

void fn1( void ), fn2( void ), fn3( void ), fn4( void );

int main( void )
{
   atexit( fn1 );
   atexit( fn2 );
   atexit( fn3 );
   atexit( fn4 );
   printf( "This is executed first.\n" );
}

void fn1()
{
   printf( "next.\n" );
}

void fn2()
{
   printf( "executed " );
}

void fn3()
{
   printf( "is " );
}

void fn4()
{
   printf( "This " );
}
```

```Output
This is executed first.
This is executed next.
```

## <a name="see-also"></a>関連項目

[プロセスと環境の制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[取り消し](abort.md)<br/>
[終了、_Exit、_exit](exit-exit-exit.md)<br/>
[_onexit、_onexit_m](onexit-onexit-m.md)<br/>
