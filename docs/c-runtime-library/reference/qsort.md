---
title: qsort
ms.date: 4/2/2020
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 09de57e206eb6fd4a75a0a9444332136aeee0e9d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338244"
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

*base*<br/>
対象となる配列の先頭。

*数*<br/>
配列サイズ (要素数)。

*幅*<br/>
要素のサイズ (バイト単位)。

*比較*<br/>
2 つの配列要素を比較してそれらの関係を指定する値を返すユーザー指定のルーチンへのポインターです。

## <a name="remarks"></a>解説

**qsort**関数は、*数値要素の*配列を並べ替えるクイックソートアルゴリズムを*実装します。* 引数*の base*は、並べ替えられる配列のベースへのポインターです。 **qsort**は、ソートされた要素を使用してこの配列を上書きします。

**qsort**は、ソート中に*比較*ルーチンを 1 回以上呼び出し、各呼び出しで 2 つの配列要素にポインターを渡します。

```C
compare( (void *) & elem1, (void *) & elem2 );
```

ルーチンは、要素を比較し、次の値のいずれかを返します。

|関数の戻り値の比較|説明|
|-----------------------------------|-----------------|
|< 0|**エレム1**未満**のエレム2**|
|0|**エレム2**に相当する**エレム**1|
|> 0|**エレム1**より大きい**2**|

配列は、比較関数による定義に従って、昇順で並べ替えられます。 配列を降順で並べ替えるには、比較関数の "より大きい" と "より小さい" の意味を入れ替えます。

この関数は、パラメーターを検証します。 *比較*または*数値*が**NULL**の場合、または*base*が NULL で**数値**が 0 以外の場合、または*幅*が 0 より小さい場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 *number* 実行を続行できる場合、関数は戻り **、errno**は**EINVAL**に設定されます。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**qsort**|\<stdlib.h > と \<search.h >|

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

[検索と並べ替え](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch](bsearch.md)<br/>
[_lsearch](lsearch.md)<br/>
