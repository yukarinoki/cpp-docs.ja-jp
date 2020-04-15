---
title: bsearch
ms.date: 4/2/2020
api_name:
- bsearch
- _o_bsearch
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
- api-ms-win-crt-utility-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- bsearch
helpviewer_keywords:
- arrays [CRT], binary search
- bsearch function
ms.assetid: e0ad2f47-e7dd-49ed-8288-870457a14a2c
ms.openlocfilehash: efad391eb2512cfa59cc3597430a84727676f27e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333800"
---
# <a name="bsearch"></a>bsearch

並べ替えられた配列のバイナリ検索を実行します。 この関数のセキュリティが強化されたバージョンについては、「[bsearch_s](bsearch-s.md)」を参照してください。

## <a name="syntax"></a>構文

```C
void *bsearch(
   const void *key,
   const void *base,
   size_t num,
   size_t width,
   int ( __cdecl *compare ) (const void *key, const void *datum)
);
```

### <a name="parameters"></a>パラメーター

*キー*\
検索するキーへのポインター。

*ベース*\
検索データのベースへのポインター。

*数*\
要素の数。

*幅*\
要素の幅。

*比較*\
2 つの要素を比較するコールバック関数。 1 つ目は検索用のキーへのポインターで、2 つ目はキーと比較する配列要素へのポインターです。

## <a name="return-value"></a>戻り値

**bsearch**は *、base*が指す配列内の*キー*の出現を指すポインタを返します。 *key*が見つからない場合、関数は**NULL**を返します。 配列が昇順でないか、同一キーで重複するレコードがある場合、結果は予測不可能になります。

## <a name="remarks"></a>解説

**bsearch**関数は、ソートされた*数値*要素の配列 (サイズの*幅*の各バイト) のバイナリ検索を実行します。 *基本*値は、検索対象の配列のベースへのポインタであり、*キー*は求められている値です。 *compare*パラメーターは、要求されたキーと配列要素を比較するユーザー指定ルーチンへのポインターです。 このメソッドは、リレーションシップを指定する次のいずれかの値を返します。

|*比較*ルーチンによって返される値|説明|
|-----------------------------------------|-----------------|
|\< 0|キーは配列要素より小さい。|
|0|キーは配列要素と等しい。|
|> 0|キーは配列要素より大きい。|

この関数は、パラメーターを検証します。 *比較*、*キー*または*数値*が**NULL**の場合、*または base*が**NULL で数値***が*0 以外の場合、または*幅*が 0 の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合は**errno**がに`EINVAL`設定され、関数は**NULL**を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**bsearch**|\<stdlib.h > と \<search.h >|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

このプログラムでは、qsort で文字列の配列を並べ替え、bsearch を使用して "cat" という単語を検索します。

```C
// crt_bsearch.c
#include <search.h>
#include <string.h>
#include <stdio.h>

int compare( char **arg1, char **arg2 )
{
   /* Compare all of both strings: */
   return _strcmpi( *arg1, *arg2 );
}

int main( void )
{
   char *arr[] = {"dog", "pig", "horse", "cat", "human", "rat", "cow", "goat"};
   char **result;
   char *key = "cat";
   int i;

   /* Sort using Quicksort algorithm: */
   qsort( (void *)arr, sizeof(arr)/sizeof(arr[0]), sizeof( char * ), (int (*)(const
   void*, const void*))compare );

   for( i = 0; i < sizeof(arr)/sizeof(arr[0]); ++i )    /* Output sorted list */
      printf( "%s ", arr[i] );

   /* Find the word "cat" using a binary search algorithm: */
   result = (char **)bsearch( (char *) &key, (char *)arr, sizeof(arr)/sizeof(arr[0]),
                              sizeof( char * ), (int (*)(const void*, const void*))compare );
   if( result )
      printf( "\n%s found at %Fp\n", *result, result );
   else
      printf( "\nCat not found!\n" );
}
```

```Output
cat cow dog goat horse human pig rat
cat found at 002F0F04
```

## <a name="see-also"></a>関連項目

[検索と並べ替え](../../c-runtime-library/searching-and-sorting.md)\
[_lfind](lfind.md)\
[_lsearch](lsearch.md)\
[qsort](qsort.md)
