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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: a093dbdbc4849b1c2f3d86e85a5e2b25a7b988e2
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836661"
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

**malloc** は、割り当てられた領域への void ポインターを返します。または、使用可能なメモリが不足している場合は **NULL** を返します。 以外の型へのポインターを返すには、 **`void`** 戻り値に型キャストを使用します。 戻り値が指すストレージ領域は、オブジェクトのアラインメント要件が基本的なアラインメントの要件以下である限り、どの型のオブジェクトを格納する場合でも、適切なアラインメントが保証されます  (Visual C++ では、基本的なアラインメントとして **`double`** 、または8バイトのアラインメントが必要です。 64ビットプラットフォームを対象とするコードでは、16バイトです)。 [_Aligned_malloc](aligned-malloc.md) を使用して、より大きなアラインメント要件を持つオブジェクトのストレージを割り当てます。たとえば、SSE 型 [__m128](../../cpp/m128.md) や **`__m256`** 、n を使用して宣言された型 ( `__declspec(align( n ))` **n** は8より大きい) などです。 *Size*が0の場合、 **malloc**はヒープに長さが0のアイテムを割り当て、そのアイテムへの有効なポインターを返します。 要求されたメモリの量が少ない場合でも、 **malloc**からの戻り値を常に確認してください。

## <a name="remarks"></a>解説

**Malloc**関数は、*サイズ*が少なくともバイトのメモリブロックを割り当てます。 アラインメントとメンテナンスの情報に必要な領域により、ブロックの *サイズ* がバイトを超えている可能性があります。

メモリ割り当てが失敗した場合、または要求されたメモリの量が **_HEAP_MAXREQ**を超えた場合、 **malloc**は**errno**を**ENOMEM**に設定します。 このエラー コードと他のエラーコードの詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

スタートアップコードは **malloc** を使用して、 **_environ**、 *envp*、および *argv* 変数のストレージを割り当てます。 次の関数とそれに対応するワイド文字も **malloc**を呼び出します。

:::row:::
   :::column span="":::
      [calloc](calloc.md)\
      [_exec 関数](../../c-runtime-library/exec-wexec-functions.md)\
      [fgetc](fgetc-fgetwc.md)\
      [_fgetchar](fgetc-fgetwc.md)\
      [fgets](fgets-fgetws.md)\
      [fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md)\
      [fputc](fputc-fputwc.md)\
      [_fputchar](fputc-fputwc.md)\
      [fputs](fputs-fputws.md)\
      [fread](fread.md)
   :::column-end:::
   :::column span="":::
      [fscanf](fscanf-fscanf-l-fwscanf-fwscanf-l.md)\
      [fseek](fseek-fseeki64.md)\
      [fsetpos](fsetpos.md)\
      [_fullpath](fullpath-wfullpath.md)\
      [fwrite](fwrite.md)\
      [getc](getc-getwc.md)\
      [getchar](getc-getwc.md)\
      [_getcwd](getcwd-wgetcwd.md)\
      [_getdcwd](getcwd-wgetcwd.md)\
      [値](../../c-runtime-library/gets-getws.md)
   :::column-end:::
   :::column span="":::
      [_getw](getw.md)\
      [_popen](popen-wpopen.md)\
      [printf](printf-printf-l-wprintf-wprintf-l.md)\
      [putc](putc-putwc.md)\
      [putchar](putc-putwc.md)\
      [_putenv](putenv-wputenv.md)\
      [ボード](puts-putws.md)\
      [_putw](putw.md)\
      [scanf](scanf-scanf-l-wscanf-wscanf-l.md)
   :::column-end:::
   :::column span="":::
      [_searchenv](searchenv-wsearchenv.md)\
      [setvbuf](setvbuf.md)\
      [_spawn 関数](../../c-runtime-library/spawn-wspawn-functions.md)\
      [_strdup](strdup-wcsdup-mbsdup.md)\
      [system](system-wsystem.md)\
      [_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)\
      [ungetc](ungetc-ungetwc.md)\
      [vfprintf](vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)\
      [vprintf](vprintf-vprintf-l-vwprintf-vwprintf-l.md)
   :::column-end:::
:::row-end:::

C++ の [_set_new_mode](set-new-mode.md) 関数は、**malloc** 用の新しいハンドラー モードを設定します。 新しいハンドラーモードは、エラー発生時に **malloc** が [_set_new_handler](set-new-handler.md)によって設定された新しいハンドラールーチンを呼び出すかどうかを示します。 既定では、 **malloc** は、メモリの割り当てに失敗したときに新しいハンドラールーチンを呼び出しません。 この既定の動作を無効にすると、 **malloc** がメモリの割り当てに失敗したときに、 **malloc** は、同じ理由で失敗したときと同じ方法で新しいハンドラールーチンを呼び出します **`new`** 。 既定値をオーバーライドするに `_set_new_mode(1)` は、プログラムの早い段階でを呼び出すか、NEWMODE を使用してリンクします。OBJ (「 [リンクオプション](../../c-runtime-library/link-options.md)」を参照)。

アプリケーションが C ランタイムライブラリのデバッグバージョンにリンクされている場合、 **malloc** は [_malloc_dbg](malloc-dbg.md)に解決されます。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。

**malloc** はとマークされてい `__declspec(noalias)` `__declspec(restrict)` ます。これは、関数がグローバル変数を変更せず、返されるポインターがエイリアス化されていないことを保証することを意味します。 詳細については、「[noalias](../../cpp/noalias.md)」、および「[restrict](../../cpp/restrict.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**malloc**|\<stdlib.h> および \<malloc.h>|

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

[メモリの割り当て](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[空け](free.md)<br/>
[realloc](realloc.md)<br/>
[_aligned_malloc](aligned-malloc.md)<br/>
