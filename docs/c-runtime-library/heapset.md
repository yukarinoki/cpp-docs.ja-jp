---
title: _heapset
ms.date: 11/04/2016
apiname:
- _heapset
apilocation:
- msvcr90.dll
- msvcr80.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr120.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- _heapset
- heapset
helpviewer_keywords:
- checking heap
- heapset function
- heaps, checking
- debugging [CRT], heap-related problems
- _heapset function
ms.assetid: 9667eeb0-55bc-4c19-af5f-d1fd0a142b3c
ms.openlocfilehash: c93624b8b56fb53eb15263dbd0d203cd9130eacf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528194"
---
# <a name="heapset"></a>_heapset

ヒープの最小限の一貫性をチェックし、空きエントリを指定した値に設定します。

> [!IMPORTANT]
>  これは古い関数です。 Visual Studio 2015 以降、CRT で使用できません。

## <a name="syntax"></a>構文

```
int _heapset(
   unsigned int fill
);
```

#### <a name="parameters"></a>パラメーター

*fill*<br/>
充填文字。

## <a name="return-value"></a>戻り値

`_heapset` は、Malloc.h に定義されている次の整数のマニフェスト定数のいずれかを返します。

|||
|-|-|
| `_HEAPBADBEGIN`  | 初期ヘッダー情報が無効または見つかりません。  |
| `_HEAPBADNODE`  | ヒープが破損しているか、不適切なノードが見つかりました。  |
| `_HEAPEMPTY`  | ヒープが初期化されていません。  |
| `_HEAPOK`  | ヒープは一貫性があると思われます。  |

また、エラーが発生した場合、`_heapset` は `errno` を `ENOSYS` に設定します。

## <a name="remarks"></a>コメント

`_heapset` 関数は、誤って上書きされた空きメモリの場所またはノードを示します。

`_heapset` は、ヒープの最小限の一貫性をチェックし、ヒープの空きエントリの各バイトに `fill` 値を設定します。 この既知の値は、空きノードがあるヒープのメモリ位置を示すとともに、解放されたメモリに誤って書き込まれたデータを含むのはどれかを示します。 オペレーティング システムで `_heapset` がサポートされていない場合 (Windows 98 など)、この関数は `_HEAPOK` を返し、`errno` を `ENOSYS` に設定します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|`_heapset`|\<malloc.h>|\<errno.h>|

互換性について詳しくは、概要の「[互換性](../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```
// crt_heapset.c
// This program checks the heap and
// fills in free entries with the character 'Z'.

#include <malloc.h>
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int heapstatus;
   char *buffer;

   if( (buffer = malloc( 1 )) == NULL ) // Make sure heap is
      exit( 0 );                        //    initialized
   heapstatus = _heapset( 'Z' );        // Fill in free entries
   switch( heapstatus )
   {
   case _HEAPOK:
      printf( "OK - heap is fine\n" );
      break;
   case _HEAPEMPTY:
      printf( "OK - heap is empty\n" );
      break;
   case _HEAPBADBEGIN:
      printf( "ERROR - bad start of heap\n" );
      break;
   case _HEAPBADNODE:
      printf( "ERROR - bad node in heap\n" );
      break;
   }
   free( buffer );
}
```

```Output
OK - heap is fine
```

## <a name="see-also"></a>参照

[メモリ割り当て](../c-runtime-library/memory-allocation.md)<br/>
[_heapadd](../c-runtime-library/heapadd.md)<br/>
[_heapchk](../c-runtime-library/reference/heapchk.md)<br/>
[_heapmin](../c-runtime-library/reference/heapmin.md)<br/>
[_heapwalk](../c-runtime-library/reference/heapwalk.md)