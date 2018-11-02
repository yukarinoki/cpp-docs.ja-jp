---
title: _lfind
ms.date: 11/04/2016
apiname:
- _lfind
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- lfind
- _lfind
helpviewer_keywords:
- linear searching
- lfind function
- arrays [CRT], searching
- searching, linear
- finding keys in arrays
- _lfind function
ms.assetid: a40ece70-1674-4b75-94bd-9f57cfff18f2
ms.openlocfilehash: 1508d54d6b2f2566e4aee3afef02af45b28e4f48
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579167"
---
# <a name="lfind"></a>_lfind

指定されたキーの線形探索を実行します。 この関数のセキュリティが強化されたバージョンについては、「[_lfind_s](lfind-s.md)」を参照してください。

## <a name="syntax"></a>構文

```C
void *_lfind(
   const void *key,
   const void *base,
   unsigned int *num,
   unsigned int width,
   int (__cdecl *compare)(const void *, const void *)
);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
検索するオブジェクト。

*base*<br/>
検索データのベースへのポインター。

*数*<br/>
配列要素の数。

*width*<br/>
配列要素の幅。

*compare*<br/>
比較ルーチンへのポインター。 最初のパラメーターは、検索用のキーへのポインターです。 2 番目の引数は、キーと比較する配列要素へのポインターです。

## <a name="return-value"></a>戻り値

キーが見つかった場合 **_lfind**配列の要素へのポインターを返します*基本*と一致する*キー*します。 キーが見つからない場合 **_lfind**返します**NULL**します。

## <a name="remarks"></a>Remarks

**_Lfind**関数は、値に関して線形探索を実行します。*キー*の配列の*数*の各要素は、*幅*バイト。 異なり**bsearch**、 **_lfind**配列を並べ替えるには必要ありません。 *基本*引数は、検索する配列のベースへのポインター。 *比較*引数が 2 つの配列要素を比較し、その関係を示す値を返します、ユーザー指定のルーチンへのポインター。 **_lfind**呼び出し、*比較*ルーチンを 1 つまたは複数回呼び出しごとに 2 つの配列要素へのポインターを渡す、検索中にします。 *比較*ルーチンが要素を比較し、し (つまり、要素が異なる) 0 以外の値を返す必要があります (つまり、要素が同じ場合) は 0。

この関数は、パラメーターを検証します。 場合*比較*、*キー*または*数*は**NULL**、または*基本*は**NULL**と*数*0 以外の場合、または*幅*が小さい」の説明に従って、0 よりも、無効なパラメーター ハンドラーが呼び出さは[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**errno**に設定されている**EINVAL** 、関数を返します**NULL**します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_lfind**|\<search.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_lfind.c
// This program uses _lfind to search a string array
// for an occurrence of "hello".

#include <search.h>
#include <string.h>
#include <stdio.h>

int compare(const void *arg1, const void *arg2 )
{
   return( _stricmp( * (char**)arg1, * (char**)arg2 ) );
}

int main( )
{
   char *arr[] = {"Hi", "Hello", "Bye"};
   int n = sizeof(arr) / sizeof(char*);
   char **result;
   char *key = "hello";

   result = (char **)_lfind( &key, arr,
                      &n, sizeof(char *), compare );

   if( result )
      printf( "%s found\n", *result );
   else
      printf( "hello not found!\n" );
}
```

```Output
Hello found
```

## <a name="see-also"></a>関連項目

[検索と並べ替え](../../c-runtime-library/searching-and-sorting.md)<br/>
[_lfind_s](lfind-s.md)<br/>
[bsearch](bsearch.md)<br/>
[_lsearch](lsearch.md)<br/>
[qsort](qsort.md)<br/>
