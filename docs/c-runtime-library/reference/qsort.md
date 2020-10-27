---
title: qsort
description: Microsoft C ランタイムクイックソート API について説明します。 `qsort`
ms.date: 10/23/2020
api_name:
- qsort
- _o_qsort
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- qsort
helpviewer_keywords:
- qsort function
- quick-sort algorithm
- sorting arrays
- arrays [CRT], sorting
ms.assetid: d6cb33eb-d209-485f-8d41-229eb743c027
ms.openlocfilehash: c658ffae69cd662809eb4dac09c06b6a13f4e051
ms.sourcegitcommit: faecabcdd12ff53eb79dc0df193fc3567f2f037c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92639121"
---
# <a name="qsort"></a>qsort

クイック ソートを実行します。 この関数のセキュリティが強化されたバージョンについては、「[qsort_s](qsort-s.md)」を参照してください。

## <a name="syntax"></a>構文

```C
void qsort(
   void *base,
   size_t number,
   size_t width,
   int (__cdecl *compare )(const void *, const void *)
);
```

### <a name="parameters"></a>パラメーター

*`base`*\
対象となる配列の先頭。

*`number`*\
配列サイズ (要素数)。

*`width`*\
要素のサイズ (バイト単位)。

*`compare`*\
2 つの配列要素を比較してそれらの関係を指定する値を返すユーザー指定のルーチンへのポインターです。

## <a name="remarks"></a>解説

関数は、 **`qsort`** 要素の配列 *`number`* (バイト単位) を並べ替えるクイックソートアルゴリズムを実装し *`width`* ます。 引数 *`base`* は、並べ替えられる配列のベースへのポインターです。 **`qsort`** 並べ替えられた要素を使用して、この配列を上書きします。

**`qsort`***`compare`* 並べ替え中にルーチンを1回以上呼び出し、各呼び出しで2つの配列要素へのポインターを渡します。 が *`compare`* 2 つの要素が同じである場合、結果の並べ替えられた配列内の順序は指定されません。

```C
compare( (void *) & elem1, (void *) & elem2 );
```

ルーチンは、要素を比較し、次の値のいずれかを返します。

|関数の戻り値の比較|説明|
|-----------------------------------|-----------------|
|< 0|**`elem1`** より小さい **`elem2`**|
|0|**`elem1`** はと同じです。 **`elem2`**|
|> 0|**`elem1`** より大きい **`elem2`**|

配列は、比較関数による定義に従って、昇順で並べ替えられます。 配列を降順で並べ替えるには、比較関数の "より大きい" と "より小さい" の意味を入れ替えます。

この関数は、パラメーターを検証します。 またはがの場合、またはがでが0以外の場合、またはが0未満の場合 *`compare`* *`number`* は、 **`NULL`** *`base`* **`NULL`** *`number`* *`width`* 「パラメーターの [検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可された場合、関数はを返し、 **`errno`** はに設定され **`EINVAL`** ます。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**`qsort`**|\<stdlib.h> および \<search.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_qsort.c
// arguments: every good boy deserves favor

/* This program reads the command-line
* parameters and uses qsort to sort them. It
* then displays the sorted arguments.
*/

#include <stdlib.h>
#include <string.h>
#include <stdio.h>

int compare( const void *arg1, const void *arg2 );

int main( int argc, char **argv )
{
   int i;
   /* Eliminate argv[0] from sort: */
   argv++;
   argc--;

   /* Sort remaining args using Quicksort algorithm: */
   qsort( (void *)argv, (size_t)argc, sizeof( char * ), compare );

   /* Output sorted list: */
   for( i = 0; i < argc; ++i )
      printf( " %s", argv[i] );
   printf( "\n" );
}

int compare( const void *arg1, const void *arg2 )
{
   /* Compare all of both strings: */
   return _stricmp( * ( char** ) arg1, * ( char** ) arg2 );
}
```

```Output
boy deserves every favor good
```

## <a name="see-also"></a>関連項目

[検索と並べ替え](../../c-runtime-library/searching-and-sorting.md)\
[`bsearch`](bsearch.md)\
[`_lsearch`](lsearch.md)
