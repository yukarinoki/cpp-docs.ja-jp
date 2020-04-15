---
title: malloc
ms.date: 4/2/2020
api_name:
- malloc
- _o_malloc
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
- api-ms-win-crt-heap-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- malloc
helpviewer_keywords:
- malloc function
- memory allocation
ms.assetid: 144fcee2-be34-4a03-bb7e-ed6d4b99eea0
ms.openlocfilehash: afe9264351110bc062d6168ef803fa6fb796538a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341574"
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

*サイズ*<br/>
割り当てるバイト数。

## <a name="return-value"></a>戻り値

**malloc**は、割り当てられたスペースへの void ポインターを戻し、使用可能なメモリーが不足している場合は**NULL を**戻します。 void 以外の型へのポインターを返す場合**は、** 戻り値にキャストする型を使用します。 戻り値が指すストレージ領域は、オブジェクトのアラインメント要件が基本的なアラインメントの要件以下である限り、どの型のオブジェクトを格納する場合でも、適切なアラインメントが保証されます  Visual C++ では、基本的な配置は、**倍**精度浮動小数点数 (8 バイト) に必要な配置です。 64 ビット プラットフォームを対象とするコードでは、16 バイトです。[_aligned_malloc](aligned-malloc.md)使用して、より大きな整列要件を持つオブジェクト (たとえば、sse タイプ[__m128](../../cpp/m128.md)と **__m256**など) と`__declspec(align( n ))`、 **n**が 8 より大きい場所で宣言された型にストレージを割り当てます。 *size が*0 の場合 **、malloc**はヒープに長さ 0 の項目を割り当て、その項目への有効なポインターを戻します。 要求されたメモリの量が少ない場合でも、必ず**malloc**からのリターンをチェックしてください。

## <a name="remarks"></a>解説

**malloc**関数は、バイトの*サイズ*が少なくとも 1 つのメモリー・ブロックを割り当てます。 配置と保守の情報に必要な領域が原因で、ブロックが*サイズ*バイトより大きくなる可能性があります。

**malloc は**、メモリ割り当てが失敗した場合、または要求されたメモリの量が _HEAP_MAXREQ を超えた場合に **、errno**を**ENOMEM** **に**設定します。 このエラー コードと他のエラーコードの詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

スタートアップ コードは**malloc**を使用して **、_environ**、 *envp*、*および argv*変数のストレージを割り当てます。 次の関数とそのワイド文字の対応も**malloc**と呼びます。

|||||
|-|-|-|-|
|[calloc](calloc.md)|[fscanf](fscanf-fscanf-l-fwscanf-fwscanf-l.md)|[_getw](getw.md)|[setvbuf](setvbuf.md)|
|[_exec 関数](../../c-runtime-library/exec-wexec-functions.md)|[fseek](fseek-fseeki64.md)|[_popen](popen-wpopen.md)|[_spawn 関数](../../c-runtime-library/spawn-wspawn-functions.md)|
|[fgetc](fgetc-fgetwc.md)|[fsetpos](fsetpos.md)|[printf](printf-printf-l-wprintf-wprintf-l.md)|[_strdup](strdup-wcsdup-mbsdup.md)|
|[_fgetchar](fgetc-fgetwc.md)|[_fullpath](fullpath-wfullpath.md)|[putc](putc-putwc.md)|[システム](system-wsystem.md)|
|[fgets](fgets-fgetws.md)|[fwrite](fwrite.md)|[putchar](putc-putwc.md)|[_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|
|[fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[getc](getc-getwc.md)|[_putenv](putenv-wputenv.md)|[ungetc](ungetc-ungetwc.md)|
|[fputc](fputc-fputwc.md)|[Getchar](getc-getwc.md)|[puts](puts-putws.md)|[vfprintf](vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|
|[_fputchar](fputc-fputwc.md)|[_getcwd](getcwd-wgetcwd.md)|[_putw](putw.md)|[vprintf](vprintf-vprintf-l-vwprintf-vwprintf-l.md)|
|[fputs](fputs-fputws.md)|[_getdcwd](getcwd-wgetcwd.md)|[scanf](scanf-scanf-l-wscanf-wscanf-l.md)||
|[fread](fread.md)|[取得する](../../c-runtime-library/gets-getws.md)|[_searchenv](searchenv-wsearchenv.md)||

C++ の [_set_new_mode](set-new-mode.md) 関数は、**malloc** 用の新しいハンドラー モードを設定します。 新しいハンドラ モードは、失敗時に**malloc**が[_set_new_handler](set-new-handler.md)で設定された新しいハンドラ ルーチンを呼び出すかどうかを示します。 既定では **、malloc**はメモリの割り当てに失敗した場合に新しいハンドラー ルーチンを呼び出しません。 **malloc**がメモリの割り当てに失敗した場合に **、malloc**が new ハンドラールーチンを呼び出すのと同じ理由で失敗した場合と同じ方法で、malloc が**新しい**ハンドラー・ルーチンを呼び出すようになります。 デフォルトをオーバーライドするには、プログラム`_set_new_mode(1)`の早い段階で呼び出すか、NEWMODE を使用してリンクします。OBJ ([リンクオプション](../../c-runtime-library/link-options.md)を参照)。

アプリケーションが C ランタイム ライブラリのデバッグ バージョンにリンクされると **、malloc**は[_malloc_dbg](malloc-dbg.md)に解決します。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。

**malloc**は`__declspec(noalias)`マーク`__declspec(restrict)`され、 ;つまり、関数はグローバル変数を変更しないこと、および返されるポインターはエイリアスされないことが保証されます。 詳細については、「[noalias](../../cpp/noalias.md)」、および「[restrict](../../cpp/restrict.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**malloc**|\<stdlib.h> と \<malloc.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
[無料](free.md)<br/>
[realloc](realloc.md)<br/>
[_aligned_malloc](aligned-malloc.md)<br/>
