---
title: malloc
ms.date: 11/04/2016
apiname:
- malloc
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- malloc
helpviewer_keywords:
- malloc function
- memory allocation
ms.assetid: 144fcee2-be34-4a03-bb7e-ed6d4b99eea0
ms.openlocfilehash: e6a007fb6f089ebf1c9f5fc9ce59cbcbf0b13888
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50520368"
---
# <a name="malloc"></a>malloc

メモリ ブロックを割り当てます。

## <a name="syntax"></a>構文

```C
void *malloc(
   size_t size
);
```

### <a name="parameters"></a>パラメーター

*size*<br/>
割り当てるバイト数。

## <a name="return-value"></a>戻り値

**malloc**割り当て済みの領域に void ポインターを返しますまたは**NULL**が不足しているメモリが使用可能な場合。 以外の型へのポインターを返す**void**型、戻り値のキャストを使用します。 戻り値が指すストレージ領域は、オブジェクトのアラインメント要件が基本的なアラインメントの要件以下である限り、どの型のオブジェクトを格納する場合でも、適切なアラインメントが保証されます  (Visual C は、基本的なアラインメントは配置のために必要な**二重**、または 8 バイト。 64 ビット プラットフォームを対象としたコードでは 16 バイトです)。使用[_aligned_malloc](aligned-malloc.md)大規模な配置要件を持つオブジェクトの記憶域を割り当てる — たとえば、SSE 型[_ _m128](../../cpp/m128.md)と **__m256**、および種類が使用して宣言`__declspec(align( n ))`場所**n**が 8 より大きい。 場合*サイズ*は 0 です。 **malloc**長さ 0 のアイテムをヒープに割り当て、そのアイテムに有効なポインターを返します。 戻り値は常にチェック**malloc**要求されたメモリの量が少ない場合でも、します。

## <a name="remarks"></a>Remarks

**Malloc**関数以上のメモリ ブロックを割り当てます*サイズ*バイト。 ブロックはより大きくすることがあります*サイズ*アラインメントと保守情報に必要な領域 (バイト)。

**malloc**設定**errno**に**ENOMEM**メモリ割り当てが失敗した場合、または、要求されたメモリ量を超える場合 **_HEAP_MAXREQ**します。 このエラー コードと他のエラーコードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

スタートアップ コードを使用して**malloc**ストレージを割り当て、 **_environ**、 *envp*、および*argv*変数。 次の関数と対応するワイド文字の呼び出しも**malloc**します。

|||||
|-|-|-|-|
|[calloc](calloc.md)|[fscanf](fscanf-fscanf-l-fwscanf-fwscanf-l.md)|[_getw](getw.md)|[setvbuf](setvbuf.md)|
|[_exec 関数](../../c-runtime-library/exec-wexec-functions.md)|[fseek](fseek-fseeki64.md)|[_popen](popen-wpopen.md)|[_spawn 関数](../../c-runtime-library/spawn-wspawn-functions.md)|
|[fgetc](fgetc-fgetwc.md)|[fsetpos](fsetpos.md)|[printf](printf-printf-l-wprintf-wprintf-l.md)|[_strdup](strdup-wcsdup-mbsdup.md)|
|[_fgetchar](fgetc-fgetwc.md)|[_fullpath](fullpath-wfullpath.md)|[putc](putc-putwc.md)|[system](system-wsystem.md)|
|[fgets](fgets-fgetws.md)|[fwrite](fwrite.md)|[putchar](putc-putwc.md)|[_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|
|[fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[getc](getc-getwc.md)|[_putenv](putenv-wputenv.md)|[ungetc](ungetc-ungetwc.md)|
|[fputc](fputc-fputwc.md)|[getchar](getc-getwc.md)|[puts](puts-putws.md)|[vfprintf](vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|
|[_fputchar](fputc-fputwc.md)|[_getcwd](getcwd-wgetcwd.md)|[_putw](putw.md)|[vprintf](vprintf-vprintf-l-vwprintf-vwprintf-l.md)|
|[fputs](fputs-fputws.md)|[_getdcwd](getcwd-wgetcwd.md)|[scanf](scanf-scanf-l-wscanf-wscanf-l.md)||
|[fread](fread.md)|[gets](../../c-runtime-library/gets-getws.md)|[_searchenv](searchenv-wsearchenv.md)||

C++ の [_set_new_mode](set-new-mode.md) 関数は、**malloc** 用の新しいハンドラー モードを設定します。 新しいハンドラー モードを示すかどうか、失敗した場合、 **malloc**によって設定された新しいハンドラー ルーチンを呼び出すには、 [_set_new_handler](set-new-handler.md)します。 既定では、 **malloc**でメモリの割り当ての失敗によって新しいハンドラー ルーチンを呼び出しません。 この既定の動作をオーバーライドするように、 **malloc** 、メモリの割り当てに失敗した**malloc**に同じ新しいハンドラー ルーチンを呼び出す方法、**新しい**演算子が同じ理由で失敗しました。 既定値を上書きするには、呼び出す`_set_new_mode(1)`に、プログラム、NEWMODE にリンクします。OBJ (を参照してください[リンク オプション](../../c-runtime-library/link-options.md))。

アプリケーションが、C ランタイム ライブラリのデバッグ バージョンにリンクされている場合**malloc**に解決される[_malloc_dbg](malloc-dbg.md)します。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。

**malloc**がマークされている`__declspec(noalias)`と`__declspec(restrict)`; これは、関数は、グローバル変数を変更しないように保証を返されるポインターがエイリアス化されないことを意味します。 詳細については、「[noalias](../../cpp/noalias.md)」、および「[restrict](../../cpp/restrict.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**malloc**|\<stdlib.h> と \<malloc.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

```C
// crt_malloc.c
// This program allocates memory with
// malloc, then frees the memory with free.

#include <stdlib.h>   // For _MAX_PATH definition
#include <stdio.h>
#include <malloc.h>

int main( void )
{
   char *string;

   // Allocate space for a path name
   string = malloc( _MAX_PATH );

   // In a C++ file, explicitly cast malloc's return.  For example,
   // string = (char *)malloc( _MAX_PATH );

   if( string == NULL )
      printf( "Insufficient memory available\n" );
   else
   {
      printf( "Memory space allocated for path name\n" );
      free( string );
      printf( "Memory freed\n" );
   }
}
```

```Output
Memory space allocated for path name
Memory freed
```

## <a name="see-also"></a>関連項目

[メモリ割り当て](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
[_aligned_malloc](aligned-malloc.md)<br/>
