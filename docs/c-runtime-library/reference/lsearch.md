---
title: _lsearch
ms.date: 4/2/2020
api_name:
- _lsearch
- _o__lsearch
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
- _lsearch
helpviewer_keywords:
- _lsearch function
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- linear searches
- searching, linear
- lsearch function
ms.assetid: 8200f608-159a-46f0-923b-1a37ee1af7e0
ms.openlocfilehash: a6ef3d86ffe8f03da34d4a374bddda1452815672
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341645"
---
# <a name="_lsearch"></a>_lsearch

ある値に関して一方向に検索を実行し、見つからない場合はリストの末尾に追加します。 この関数のセキュリティが強化されたバージョンについては、「[_lsearch_s](lsearch-s.md)」をご覧ください。

## <a name="syntax"></a>構文

```C
void *_lsearch(
   const void *key,
   void *base,
   unsigned int *num,
   unsigned int width,
   int (__cdecl *compare)(const void *, const void *)
);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
検索するオブジェクト。

*base*<br/>
検索する配列のベースへのポインター。

*数*<br/>
要素の数。

*幅*<br/>
配列の各要素の幅。

*比較*<br/>
比較ルーチンへのポインター。 最初のパラメーターは、検索用のキーへのポインターです。 2 番目のパラメーターは、そのキーと比較する配列要素へのポインターです。

## <a name="return-value"></a>戻り値

キーが見つかった場合 **、_lsearch**は *、key*に一致する*配列*の要素へのポインターを返します。 キーが見つからない場合 **、_lsearch**は配列の末尾に新しく追加された項目へのポインターを返します。

## <a name="remarks"></a>解説

**_lsearch**関数は、*数値要素の*配列 (*幅*のバイトの各配列) の値*キー*のリニア検索を実行します。 **bsearch**とは異なり **、_lsearch**配列をソートする必要はありません。 *key*が見つからない場合 **、_lsearch**は配列の末尾に追加し、*数値*をインクリメントします。

*compare*引数は、2 つの配列要素を比較し、それらの関係を指定する値を返すユーザー提供ルーチンへのポインターです。 **_lsearch**は、検索中に*比較*ルーチンを 1 回以上呼び出し、各呼び出しで 2 つの配列要素へのポインターを渡します。 *比較*では、要素を比較し、0 以外 (要素が異なることを意味します) または 0 (要素が同一であることを意味します) を返す必要があります。

この関数は、パラメーターを検証します。 *比較*、*キー*または*数値*が**NULL**の場合、*または base*が NULL で**数値***が*0 以外の場合、または*幅*が 0 未満の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合 **、errno**は**EINVAL**に設定され、関数は**NULL**を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_lsearch**|\<search.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_lsearch.c
#include <search.h>
#include <string.h>
#include <stdio.h>

int compare( const void *arg1, const void *arg2 );

int main(void)
{
   char * wordlist[4] = { "hello", "thanks", "bye" };
                            // leave room to grow...
   int n = 3;
   char **result;
   char *key = "extra";
   int i;

   printf( "wordlist before _lsearch:" );
   for( i=0; i<n; ++i ) printf( " %s", wordlist[i] );
   printf( "\n" );

   result = (char **)_lsearch( &key, wordlist,
                      &n, sizeof(char *), compare );

   printf( "wordlist after _lsearch:" );
   for( i=0; i<n; ++i ) printf( " %s", wordlist[i] );
   printf( "\n" );
}

int compare(const void *arg1, const void *arg2 )
{
   return( _stricmp( * (char**)arg1, * (char**)arg2 ) );
}
```

```Output
wordlist before _lsearch: hello thanks bye
wordlist after _lsearch: hello thanks bye extra
```

## <a name="see-also"></a>関連項目

[検索と並べ替え](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch](bsearch.md)<br/>
[_lfind](lfind.md)<br/>
[_lsearch_s](lsearch-s.md)<br/>
