---
title: _lfind
ms.date: 4/2/2020
api_name:
- _lfind
- _o__lfind
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _lfind
helpviewer_keywords:
- linear searching
- lfind function
- arrays [CRT], searching
- searching, linear
- finding keys in arrays
- _lfind function
ms.assetid: a40ece70-1674-4b75-94bd-9f57cfff18f2
ms.openlocfilehash: 287cbd8bc9cc567a4a0d5b9505d57098197bc545
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342171"
---
# <a name="_lfind"></a>_lfind

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

*幅*<br/>
配列要素の幅。

*比較*<br/>
比較ルーチンへのポインター。 最初のパラメーターは、検索用のキーへのポインターです。 2 番目の引数は、キーと比較する配列要素へのポインターです。

## <a name="return-value"></a>戻り値

キーが見つかった場合 **、_lfind**は *、key*に一致する*配列*の要素へのポインターを返します。 キーが見つからない場合 **、_lfind**は**NULL を**返します。

## <a name="remarks"></a>解説

**_lfind**関数は、*数値要素の*配列 (*幅*のバイトの各配列) の値*キー*の線形検索を実行します。 **bsearch**とは異なり **、_lfind**配列をソートする必要はありません。 *基本*引数は、検索対象の配列のベースへのポインターです。 *compare*引数は、2 つの配列要素を比較し、その関係を指定する値を返すユーザー提供ルーチンへのポインターです。 **_lfind**は、検索中に*比較*ルーチンを 1 回以上呼び出し、各呼び出しで 2 つの配列要素へのポインターを渡します。 *比較*ルーチンは、要素を比較してから、0 以外 (要素が異なることを意味します) または 0 (要素が同一であることを意味します) を返す必要があります。

この関数は、パラメーターを検証します。 *比較*、*キー*または*数値*が**NULL**の場合、*または base*が NULL で**数値***が*0 以外の場合、または*幅*が 0 未満の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合 **、errno**は**EINVAL**に設定され、関数は**NULL**を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_lfind**|\<search.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

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
