---
title: _mktemp、_wmktemp
ms.date: 11/04/2016
apiname:
- _wmktemp
- _mktemp
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: c1c5f0ee12c9e07d76405014bb4a6a6ecc7d97e6
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326265"
---
# <a name="mktemp-wmktemp"></a>_mktemp、_wmktemp

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

*nameTemplate*<br/>
ファイル名のパターン。

## <a name="return-value"></a>戻り値

これらの各関数は、変更後の nameTemplate にポインターを返します。 関数を返します**NULL**場合*nameTemplate*形式が正しくないか、これ以上の一意の名前は、特定の nameTemplate から作成できます。

## <a name="remarks"></a>Remarks

**_Mktemp**関数を変更して一意のファイル名を作成し、 *nameTemplate*引数。 **_mktemp**マルチバイト文字の文字列引数には、実行時のシステムによって現在使用中のマルチバイト コード ページに従ってマルチバイト文字シーケンスを認識するを必要に応じて、自動的に処理します。 **_wmktemp**のワイド文字バージョンは、 **_mktemp**; の引数と戻り値 **_wmktemp**はワイド文字列です。 **_wmktemp**と **_mktemp**の動作は同じ場合は、点を除いて **_wmktemp**マルチバイト文字の文字列を処理しません。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp**|**_mktemp**|**_mktemp**|**_wmktemp**|

*NameTemplate*引数の形式*基本*XXXXXX、場所*基本*提供する新しいファイル名の一部である、各 X はによって指定される文字のプレース ホルダー **_mktemp**します。 内の各プレース ホルダー文字*nameTemplate*は大文字の X をする必要があります **_mktemp**保持*基本*し、最初の後続の X を英字に置き換えます。 **_mktemp**末尾の次を置換する大文字の X を 5 桁の値です。 この値は、プロセス、またはマルチ スレッド プログラムの場合は、呼び出し元のスレッドには、呼び出し元を識別する一意の番号。

呼び出しが成功した **_mktemp**変更*nameTemplate*します。 各後続の呼び出しと同じプロセスまたは同じスレッドで*nameTemplate*引数、 **_mktemp**によって返される名前と一致するファイル名に対してチェック **_mktemp**で前の呼び出し。 指定した名前のファイルが存在しない場合 **_mktemp**その名前を返します。 名前、以前に返したすべてのファイルが存在する場合 **_mktemp**英字部分 'a' ~ 'z' の順序で、[次へ] の使用可能な小文字文字を置き換えることで、新しい名前を作成します。 たとえば場合、*基本*は。

> **fn**

によって提供される 5 桁の値と **_mktemp**返される最初の名前が 12345 の場合。

> **fna12345**

この名前を使用してファイル FNA12345 を作成しており、このファイルが存在する同じプロセスまたはスレッドで、同じ呼び出しで、[次へ] の名前が返されます場合*基本*の*nameTemplate*は。

> **fnb12345**

FNA12345 が存在しない場合、次に返される名前はもう一度次のようになります。

> **fna12345**

**_mktemp**の任意の組み合わせの 26 の一意のファイル名の最大値を作成できます*基本*と*nameTemplate*値。 そのため、FNZ12345 は、最後の一意のファイル名 **_mktemp**を作成することができます、*基本*と*nameTemplate*この例で使用される値。

失敗した場合、 **errno**設定されます。 場合*nameTemplate*形式が無効です (6 より少ないなどの X)、 **errno**に設定されている**EINVAL**します。 場合 **_mktemp** 26 のすべての使用可能なファイル名が既に存在するために、一意の名前を作成するようになって **_mktemp** nameTemplate を空の文字列に設定し、返します**EEXIST**します。

C++ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_mktemp**|\<io.h>|
|**_wmktemp**|\<io.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
