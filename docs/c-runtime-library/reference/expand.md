---
title: _expand | Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _expand
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
- _bexpand
- fexpand
- expand
- nexpand
- _fexpand
- _nexpand
- bexpand
- _expand
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, changing size
- _expand function
- expand function
ms.assetid: 4ac55410-39c8-45c7-bccd-3f1042ae2ed3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f709df131ded856881dc171c2e1549d3d5d378e1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32402352"
---
# <a name="expand"></a>_expand

メモリ ブロックのサイズを変更します。

## <a name="syntax"></a>構文

```C
void *_expand(
   void *memblock,
   size_t size
);
```

### <a name="parameters"></a>パラメーター

*_expand*<br/>
以前に割り当てられたメモリ ブロックへのポインター。

*size*<br/>
新しいサイズ (バイト単位)。

## <a name="return-value"></a>戻り値

**_expand**再割り当てされたメモリ ブロックへの void ポインターを返します。 **_expand**とは異なり、 **realloc**、そのサイズを変更するブロックを移動することはできません。 したがって、移動せず、ブロックを展開できる十分なメモリがある場合は、 *_expand*パラメーターを **_expand**戻り値と同じです。

**_expand**返します**NULL**その操作中にエラーが検出された場合。 たとえば場合、 **_expand**はメモリ ブロックを縮小するために使用、可能性があります、少量のヒープや無効なブロック ポインターの破損を検出し、返す**NULL**です。

この関数を返しますのかどうかは、移動することがなく、特定のサイズにブロックを拡張する使用可能なメモリが不足して、 **NULL**です。 **_expand**サイズに拡張されるよりも小さい要求されたブロックを返しません。 失敗した場合、 **errno**エラーの性質を示すです。 詳細については**errno**を参照してください[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)です。

戻り値は、どの型のオブジェクトを格納する場合でも適切なアラインメントが保証されるストレージ領域を指します。 確認するには、項目の新しいサイズを使用して **_msize**です。 以外の型へのポインターを取得する**void**型、戻り値のキャストを使用します。

## <a name="remarks"></a>コメント

**_Expand**関数を拡張またはヒープ内の場所を移動せず、ブロックを縮小しようとしています。 以前に割り当てられたメモリ ブロックのサイズを変更します。 *_Expand*パラメーターは、ブロックの先頭を指します。 *サイズ*パラメーターは、ブロックの新しいサイズをバイトで示します。 ブロックの内容は、新しいサイズと古いサイズのうち小さい方のサイズまでは変更されません。 *_expand*解放されたブロックをすることはできません。

> [!NOTE]
> 64 ビット プラットフォームでは、 **_expand**可能性がありますいないコントラクトのブロック、ブロックのサイズは 16 K 未満、したがって Low Fragmentation Heap に割り当てられている場合、新しいサイズが現在のサイズより以外の場合は特に、小さい場合 **_expand**が変更されていないブロックを離れるし、返します *_expand*です。

C ランタイム ライブラリのデバッグ バージョンとリンクするアプリケーション **_expand**に解決される[_expand_dbg](expand-dbg.md)です。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。

この関数は、パラメーターを検証します。 場合 *_expand* null ポインター」の説明に従って、この関数は、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**errno**に設定されている**EINVAL** 、関数を返します**NULL**です。 場合*サイズ*がより大きい **_HEAP_MAXREQ**、 **errno**に設定されている**ENOMEM** 、関数を返します**NULL**.

## <a name="requirements"></a>要件

|関数|必須ヘッダー|
|--------------|---------------------|
|**_expand**|\<malloc.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
[free](free.md)<br/>
[malloc](malloc.md)<br/>
[_msize](msize.md)<br/>
[realloc](realloc.md)<br/>
