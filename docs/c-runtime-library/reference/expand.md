---
title: _expand
ms.date: 4/2/2020
api_name:
- _expand
- _o__expand
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
- _bexpand
- fexpand
- expand
- nexpand
- _fexpand
- _nexpand
- bexpand
- _expand
helpviewer_keywords:
- memory blocks, changing size
- _expand function
- expand function
ms.assetid: 4ac55410-39c8-45c7-bccd-3f1042ae2ed3
ms.openlocfilehash: 7f2a789bc5f475411808bc00a4280b7573b67cf2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347558"
---
# <a name="_expand"></a>_expand

メモリ ブロックのサイズを変更します。

## <a name="syntax"></a>構文

```C
void *_expand(
   void *memblock,
   size_t size
);
```

### <a name="parameters"></a>パラメーター

*memblock*<br/>
以前に割り当てられていたメモリ ブロックへのポインター。

*サイズ*<br/>
新しいサイズ (バイト単位)。

## <a name="return-value"></a>戻り値

**_expand**は、再割り当てされたメモリ ブロックへの void ポインターを返します。 **_expand** **_expand、realloc**とは異なり、ブロックを移動してサイズを変更することはできません。 したがって、ブロックを移動せずに拡張できるメモリが十分にある場合 **、_expand**する*memblock*パラメータは戻り値と同じです。

**_expand**操作中にエラーが検出されると**NULL が**返されます。 たとえば **、_expand**を使用してメモリ ブロックを縮小すると、小さなブロック ヒープまたは無効なブロック ポインタの破損が検出され **、NULL が**返される場合があります。

ブロックを移動せずに指定されたサイズに拡張するために使用できるメモリが不足している場合、関数は**NULL**を返します。 **_expand**は、要求されたサイズより小さいサイズに拡張されたブロックを返しません。 エラーが発生した場合 **、errno**は障害の性質を示します。 **errno**の詳細については、「 [errno 、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

戻り値は、どの型のオブジェクトを格納する場合でも適切なアラインメントが保証されるストレージ領域を指します。 項目の新しいサイズを確認するには、 **_msize**を使用します。 void 以外の型へのポインターを取得するには **、** 戻り値にキャストする型を使用します。

## <a name="remarks"></a>解説

**_expand**関数は、ヒープ内の位置を移動せずにブロックを拡張または縮小することによって、以前に割り当てられたメモリ ブロックのサイズを変更します。 *memblock*パラメータはブロックの先頭を指します。 *size*パラメーターは、ブロックの新しいサイズをバイト単位で指定します。 ブロックの内容は、新しいサイズと古いサイズのうち小さい方のサイズまでは変更されません。 *memblock*は解放されたブロックであってはなりません。

> [!NOTE]
> 64 ビット プラットフォームでは、新しいサイズが現在のサイズより小さい場合 **、_expand**はブロックを縮小しない可能性があります。特に、ブロックのサイズが 16K 未満で、低フラグメンテーション ヒープに割り当てられている場合 **、_expand**ブロックは変更されず *、memblock*を返します。

アプリケーションが C ランタイム ライブラリのデバッグ バージョンにリンクされると **、_expand**[は _expand_dbg](expand-dbg.md)に解決されます。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。

この関数は、パラメーターを検証します。 *memblock*が null ポインターの場合、この関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行を続行できる場合 **、errno**は**EINVAL**に設定され、関数は**NULL**を返します。 *size*が **_HEAP_MAXREQ**より大きい場合 **、errno**は**ENOMEM**に設定され、関数は**NULL**を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|
|--------------|---------------------|
|**_expand**|\<malloc.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_expand.c

#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>

int main( void )
{
   char *bufchar;
   printf( "Allocate a 512 element buffer\n" );
   if( (bufchar = (char *)calloc( 512, sizeof( char ) )) == NULL )
      exit( 1 );
   printf( "Allocated %d bytes at %Fp\n",
         _msize( bufchar ), (void *)bufchar );
   if( (bufchar = (char *)_expand( bufchar, 1024 )) == NULL )
      printf( "Can't expand" );
   else
      printf( "Expanded block to %d bytes at %Fp\n",
            _msize( bufchar ), (void *)bufchar );
   // Free memory
   free( bufchar );
   exit( 0 );
}
```

```Output
Allocate a 512 element buffer
Allocated 512 bytes at 002C12BC
Expanded block to 1024 bytes at 002C12BC
```

## <a name="see-also"></a>関連項目

[メモリ割り当て](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[無料](free.md)<br/>
[malloc](malloc.md)<br/>
[_msize](msize.md)<br/>
[realloc](realloc.md)<br/>
