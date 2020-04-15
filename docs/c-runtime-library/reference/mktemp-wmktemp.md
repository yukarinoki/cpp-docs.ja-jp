---
title: _mktemp、_wmktemp
ms.date: 4/2/2020
api_name:
- _wmktemp
- _mktemp
- _o__mktemp
- _o__wmktemp
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tmktemp
- wmktemp
- tmktemp
- _wmktemp
- _mktemp
helpviewer_keywords:
- _wmktemp function
- _mktemp function
- files [C++], temporary
- tmktemp function
- _tmktemp function
- wmktemp function
- mktemp function
- temporary files [C++]
ms.assetid: 055eb539-a8c2-4a7d-be54-f5b6d1eb5c85
ms.openlocfilehash: 8affd20ca7826f0d383f749567c9625d61dacd48
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338716"
---
# <a name="_mktemp-_wmktemp"></a>_mktemp、_wmktemp

一意のファイル名を作成します。 これらの関数のセキュリティを強化したバージョンについては、「[_mktemp_s、_wmktemp_s](mktemp-s-wmktemp-s.md)」をご覧ください。

## <a name="syntax"></a>構文

```C
char *_mktemp(
   char *nameTemplate
);
wchar_t *_wmktemp(
   wchar_t *nameTemplate
);
template <size_t size>
char *_mktemp(
   char (&nameTemplate)[size]
); // C++ only
template <size_t size>
wchar_t *_wmktemp(
   wchar_t (&nameTemplate)[size]
); // C++ only
```

### <a name="parameters"></a>パラメーター

*名前テンプレート*<br/>
ファイル名のパターン。

## <a name="return-value"></a>戻り値

これらの関数は、それぞれ変更された名前Templateへのポインタを返します。 nameTemplate の形式が正しくない場合、または指定された名前*から*作成できる一意の名前がなくなった場合、関数は**NULL**を返します。

## <a name="remarks"></a>解説

**_mktemp**関数は *、nameTemplate*引数を変更することによって、一意のファイル名を作成します。 **_mktemp**は、マルチバイト文字の文字列引数を適切に処理し、ランタイム システムで現在使用されているマルチバイト コード ページに従ってマルチバイト文字シーケンスを認識します。 **_wmktemp**はワイド文字の **_mktemp**バージョンです。**_wmktemp**の引数と戻り値はワイド文字列です。 **_wmktemp**と **_mktemp**は **、_wmktemp**がマルチバイト文字文字列を処理しないことを除いて、他の方法で同様に動作します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp**|**_mktemp**|**_mktemp**|**_wmktemp**|

*nameTemplate*引数には *、フォームベース*XXXXXX が *、base*は、指定した新しいファイル名の一部であり、各 X は **_mktemp**によって提供される文字のプレースホルダーです。 *nameTemplate*の各プレースホルダ文字は大文字の X である必要_mktemp*ベース***を**保持し、最初の末尾の X を英字に置き換えます。 **_mktemp**は、後続の X を 5 桁の値に置き換えます。この値は、呼び出し元のプロセス、またはマルチスレッド・プログラムの呼び出しスレッドを識別する固有の番号です。

**_mktemp**への成功した呼び出しは *、名前を変更しますテンプレート*. 同じプロセスまたは同じスレッドからの同じ*nameTemplate*引数からの呼び出しでは **、_mktemp**以前の呼び出しで **_mktemp**によって返された名前と一致するファイル名をチェックします。 指定された名前のファイルが存在しない場合 **、_mktemp**はその名前を返します。 以前に返されたすべての名前にファイルが存在する場合 **、_mktemp**は、前に返された名前で使用されていたアルファベット文字を、'a' から 'z' までの順に、次の使用可能な小文字に置き換えることによって、新しい名前を作成します。 たとえば、*ベース*が次の場合です。

> **Fn**

**_mktemp**によって提供される 5 桁の値は 12345 で、戻される最初の名前は次のようになります。

> **fna12345**

この名前を使用してファイル FNA12345 を作成しても、このファイルがまだ存在する場合、name の*同じベース*を持つ同じプロセスまたはスレッドからの呼び出しで返される次の名前は次のようになります*テンプレート:*

> **fnb12345**

FNA12345 が存在しない場合、次に返される名前はもう一度次のようになります。

> **fna12345**

**_mktemp、base**と*nameTemplate*の値の任意の組み*base*合わせに対して最大 26 個の一意のファイル名を作成できます。 したがって、FNZ12345 は、この例で使用 **_mktemp***基本*と*nameTemplate*値に対して作成できる最後の一意のファイル名です。

失敗した場合 **、errno**が設定されます。 *nameTemplate*の形式が無効な場合 (6 X 未満など **)、errno**は**EINVAL**に設定されます。 _mktemp**が**26 個のファイル名すべてが既に存在するため、一意の名前を作成できない場合 **、_mktempは**nameTemplate を空の文字列に設定し **、EEXIST**を返します。

C++ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_mktemp**|\<io.h>|
|**_wmktemp**|\<io.h> または \<wchar.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_mktemp.c
// compile with: /W3
/* The program uses _mktemp to create
* unique filenames. It opens each filename
* to ensure that the next name is unique.
*/

#include <io.h>
#include <string.h>
#include <stdio.h>
#include <errno.h>

char *template = "fnXXXXXX";
char *result;
char names[27][9];

int main( void )
{
   int i;
   FILE *fp;

   for( i = 0; i < 27; i++ )
   {
      strcpy_s( names[i], sizeof( names[i] ), template );
      /* Attempt to find a unique filename: */
      result = _mktemp( names[i] );  // C4996
      // Note: _mktemp is deprecated; consider using _mktemp_s instead
      if( result == NULL )
      {
         printf( "Problem creating the template\n" );
         if (errno == EINVAL)
         {
             printf( "Bad parameter\n");
         }
         else if (errno == EEXIST)
         {
             printf( "Out of unique filenames\n");
         }
      }
      else
      {
         fopen_s( &fp, result, "w" );
         if( fp != NULL )
            printf( "Unique filename is %s\n", result );
         else
            printf( "Cannot open %s\n", result );
         fclose( fp );
      }
   }
}
```

```Output
Unique filename is fna03912
Unique filename is fnb03912
Unique filename is fnc03912
Unique filename is fnd03912
Unique filename is fne03912
Unique filename is fnf03912
Unique filename is fng03912
Unique filename is fnh03912
Unique filename is fni03912
Unique filename is fnj03912
Unique filename is fnk03912
Unique filename is fnl03912
Unique filename is fnm03912
Unique filename is fnn03912
Unique filename is fno03912
Unique filename is fnp03912
Unique filename is fnq03912
Unique filename is fnr03912
Unique filename is fns03912
Unique filename is fnt03912
Unique filename is fnu03912
Unique filename is fnv03912
Unique filename is fnw03912
Unique filename is fnx03912
Unique filename is fny03912
Unique filename is fnz03912
Problem creating the template.
Out of unique filenames.
```

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[fopen、_wfopen](fopen-wfopen.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_getpid](getpid.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_tempnam、_wtempnam、tmpnam、_wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[tmpfile](tmpfile.md)<br/>
