---
title: _lfind | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- linear searching
- lfind function
- arrays [CRT], searching
- searching, linear
- finding keys in arrays
- _lfind function
ms.assetid: a40ece70-1674-4b75-94bd-9f57cfff18f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1f60ea8dd05f9dffd6778c001e3f150f95744ae2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
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

キーが見つかった場合、 **_lfind** 、配列の位置の要素へのポインターを返します*基本*に一致する*キー*です。 キーが見つからない場合 **_lfind**返します**NULL**です。

## <a name="remarks"></a>コメント

**_Lfind**関数値に関して線形探索を実行する*キー*の配列の*数*の各要素は、*幅*バイトです。 異なり**bsearch**、 **_lfind**に並べ替えられる配列は必要ありません。 *基本*引数は、検索対象の配列のベースへのポインター。 *比較*引数が 2 つの配列要素を比較し、後の関係を示す値を返す、ユーザーが指定したルーチンへのポインター。 **_lfind**呼び出し、*比較*ルーチンの 1 つまたは複数回呼び出しごとに 2 つの配列要素へのポインターを渡す、検索中にします。 *比較*ルーチンの要素を比較し、以外を返します。 (つまり、要素が異なります) する必要があります (つまり、要素が同一) は 0 です。

この関数は、パラメーターを検証します。 場合*比較*、*キー*または*数*は**NULL**、または*基本*null と **数* 0 以外の場合、または*幅*が小さい以上では、無効なパラメーター ハンドラーが呼び出される」の説明に従って[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**errno**に設定されている**EINVAL** 、関数を返します**NULL**です。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
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
