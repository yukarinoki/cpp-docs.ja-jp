---
title: _lsearch
ms.date: 11/04/2016
apiname:
- _lsearch
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
- _lsearch
- lsearch
helpviewer_keywords:
- _lsearch function
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- linear searches
- searching, linear
- lsearch function
ms.assetid: 8200f608-159a-46f0-923b-1a37ee1af7e0
ms.openlocfilehash: 340e8ac382972b15acc52013d5d6a51352db969c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62285657"
---
# <a name="lsearch"></a>_lsearch

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

*compare*<br/>
比較ルーチンへのポインター。 最初のパラメーターは、検索用のキーへのポインターです。 2 番目のパラメーターは、そのキーと比較する配列要素へのポインターです。

## <a name="return-value"></a>戻り値

キーが見つかった場合 **_lsearch**配列の要素へのポインターを返します*基本*と一致する*キー*します。 キーが見つからない場合 **_lsearch**配列の末尾に新しく追加された項目へのポインターを返します。

## <a name="remarks"></a>Remarks

**_Lsearch**関数は、値に関して線形探索を実行します。*キー*の配列の*数*の各要素は、*幅*バイト。 異なり**bsearch**、 **_lsearch**配列を並べ替えるには必要ありません。 場合*キー*が見つからない **_lsearch**インクリメント、配列の末尾に追加*数*します。

*比較*引数が 2 つの配列要素を比較し、それらの関係を示す値を返します、ユーザー指定のルーチンへのポインター。 **_lsearch**呼び出し、*比較*ルーチンを 1 つまたは複数回呼び出しごとに 2 つの配列要素へのポインターを渡す、検索中にします。 *比較*要素を比較し、いずれかを返す必要があります (つまり、要素が異なる) 0 以外の値または 0 (つまり、要素が同じ場合)。

この関数は、パラメーターを検証します。 場合*比較*、*キー*または*数*は**NULL**、または*基本*は**NULL**と*数*0 以外の場合、または*幅*が小さい」の説明に従って、0 よりも、無効なパラメーター ハンドラーが呼び出さは[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**errno**に設定されている**EINVAL** 、関数を返します**NULL**します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_lsearch**|\<search.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
