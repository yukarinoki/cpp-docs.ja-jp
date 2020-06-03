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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 73bc82ed57692dee348448d2b523961324203ca9
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82911328"
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

*number*<br/>
要素の数。

*width*<br/>
配列の各要素の幅。

*対照*<br/>
比較ルーチンへのポインター。 最初のパラメーターは、検索用のキーへのポインターです。 2 番目のパラメーターは、そのキーと比較する配列要素へのポインターです。

## <a name="return-value"></a>戻り値

キーが見つかった場合、 **_lsearch**は、*キー*に一致する*ベース*の配列の要素へのポインターを返します。 キーが見つからない場合、 **_lsearch**は配列の末尾に新しく追加された項目へのポインターを返します。

## <a name="remarks"></a>解説

**_Lsearch**関数は、*数値*要素の配列内の値*キー*の線形検索を実行します (各*幅*バイト)。 **Bsearch**とは異なり、 **_lsearch**では配列を並べ替える必要はありません。 *キー*が見つからない場合は、 **_lsearch**配列の末尾に追加し、*数値*をインクリメントします。

*Compare*引数は、2つの配列要素を比較し、それらの関係を指定する値を返すユーザー指定のルーチンへのポインターです。 **_lsearch**は、検索中に*比較*ルーチンを1回以上呼び出し、各呼び出しで2つの配列要素へのポインターを渡します。 *比較*では、要素を比較し、0以外 (要素が異なる場合) または 0 (要素が同じであることを意味します) のいずれかを返す必要があります。

この関数は、パラメーターを検証します。 *Compare*、 *key* 、または*number*が**null**の場合、または*base*が**null**で*数値*が0以外の場合、または*width*がゼロ未満の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可された場合、 **errno**は**EINVAL**に設定され、関数は**NULL**を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

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
