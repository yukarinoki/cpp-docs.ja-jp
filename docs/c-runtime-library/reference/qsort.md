---
title: qsort
ms.date: 11/04/2016
apiname:
- qsort
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- qsort
helpviewer_keywords:
- qsort function
- quick-sort algorithm
- sorting arrays
- arrays [CRT], sorting
ms.assetid: d6cb33eb-d209-485f-8d41-229eb743c027
ms.openlocfilehash: dd2fc9cd789b02f1fa1e0b9969b597aa51aceedd
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2018
ms.locfileid: "51327552"
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

*width*<br/>
要素のサイズ (バイト単位)。

*compare*<br/>
2 つの配列要素を比較してそれらの関係を指定する値を返すユーザー指定のルーチンへのポインターです。

## <a name="remarks"></a>Remarks

**Qsort**関数の配列を並べ替えるためのクイック ソート アルゴリズムを実装*数*の各要素は、*幅*バイト。 引数*基本*を並べ替える配列のベースへのポインターです。 **qsort**並べ替えられた要素を使用してこの配列を上書きします。

**qsort**呼び出し、*比較*日常的な 1 つまたは複数の並べ替え中にタイムアウトし、呼び出しごとに 2 つの配列要素へのポインターを渡します。

```C
compare( (void *) & elem1, (void *) & elem2 );
```

ルーチンは、要素を比較し、次の値のいずれかを返します。

|関数の戻り値の比較|説明|
|-----------------------------------|-----------------|
|< 0|**elem1**未満**elem2**|
|0|**elem1**等しく**elem2**|
|> 0|**elem1**より大きい**elem2**|

配列は、比較関数による定義に従って、昇順で並べ替えられます。 配列を降順で並べ替えるには、比較関数の "より大きい" と "より小さい" の意味を入れ替えます。

この関数は、パラメーターを検証します。 場合*比較*または*数*は**NULL**、または*基本*は**NULL**と*数* 0 以外の場合、または*幅*が小さい」の説明に従って、0 よりも、無効なパラメーター ハンドラーが呼び出さは[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 かどうかは、引き続き実行が許可された、関数を返しますと**errno**に設定されている**EINVAL**します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**qsort**|\<stdlib.h> および \<search.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
