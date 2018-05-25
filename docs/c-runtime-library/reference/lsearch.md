---
title: _lsearch | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _lsearch function
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- linear searches
- searching, linear
- lsearch function
ms.assetid: 8200f608-159a-46f0-923b-1a37ee1af7e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2aaf6626b2f7005181640f77026b6924c39cd325
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2018
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

*数*<br/>
要素の数。

*width*<br/>
配列の各要素の幅。

*compare*<br/>
比較ルーチンへのポインター。 最初のパラメーターは、検索用のキーへのポインターです。 2 番目のパラメーターは、そのキーと比較する配列要素へのポインターです。

## <a name="return-value"></a>戻り値

キーが見つかった場合、 **_lsearch** 、配列の位置の要素へのポインターを返します*基本*に一致する*キー*です。 キーが見つからない場合 **_lsearch**配列の末尾に新しく追加された項目へのポインターを返します。

## <a name="remarks"></a>コメント

**_Lsearch**関数値に関して線形探索を実行する*キー*の配列の*数*の各要素は、*幅*バイトです。 異なり**bsearch**、 **_lsearch**に並べ替えられる配列は必要ありません。 場合*キー*が見つからない **_lsearch**インクリメント、配列の末尾に追加*数*です。

*比較*引数は、ルーチンへのポインター、ユーザーが指定した 2 つの配列要素を比較し、それらの関係を示す値を返します。 **_lsearch**呼び出し、*比較*ルーチンの 1 つまたは複数回呼び出しごとに 2 つの配列要素へのポインターを渡す、検索中にします。 *比較*要素を比較し、いずれかを返す必要があります (つまり、要素が異なります) 0 以外の値または 0 (つまり、要素は同じ)。

この関数は、パラメーターを検証します。 場合*比較*、*キー*または*数*は**NULL**、または*基本*は**NULL**と*数*0 以外の場合、または*幅*が小さい以上では、無効なパラメーター ハンドラーが呼び出される」の説明に従って[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**errno**に設定されている**EINVAL** 、関数を返します**NULL**です。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
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
