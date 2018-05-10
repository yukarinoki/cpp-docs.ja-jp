---
title: _mktemp、_wmktemp | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 087348b3cc59fb1b47699fc0e64f533c22d992b4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
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

これらの各関数は、変更後の nameTemplate にポインターを返します。 この関数を返します**NULL**場合*nameTemplate*形式が正しくありませんまたは特定の nameTemplate からなくなるの一意な名前を作成できます。

## <a name="remarks"></a>コメント

**_Mktemp**関数を変更することで一意のファイル名を作成、 *nameTemplate*引数。 **_mktemp**マルチバイト文字の文字列引数には、実行時のシステムによって現在使用中のマルチバイト コード ページに基づいてマルチバイト文字シーケンスを認識することを必要に応じて自動的に処理します。 **_wmktemp**のワイド文字バージョンは、 **_mktemp**; の引数と戻り値 **_wmktemp**ワイド文字列です。 **_wmktemp**と **_mktemp**点を除いてそれ以外の場合、動作は同じ **_wmktemp**マルチバイト文字の文字列を処理しません。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp**|**_mktemp**|**_mktemp**|**_wmktemp**|

*NameTemplate*引数が、フォーム*基本 * * XXXXXX*ここで、*基本*が提供する、新しいファイル名の一部で各 X がで指定された文字のプレース ホルダー **_mktemp**です。 内の各プレース ホルダー文字*nameTemplate*大文字 X. をする必要があります **_mktemp**保持*基本*し、最初の後続の X を英字に置き換えます。 **_mktemp**末尾の次の置換 X、5 桁の値です。 この値は、プロセス、またはマルチ スレッド プログラムでは、呼び出し元のスレッド、呼び出し元を識別する一意の番号。

呼び出しが成功した **_mktemp**変更*nameTemplate*です。 各後続の呼び出し、同じプロセスまたはスレッドを同じ*nameTemplate*引数、 **_mktemp**によって返された名前に一致するファイル名の確認 **_mktemp**で以前の呼び出しです。 指定した名前のファイルが存在しない場合 **_mktemp**その名前を返します。 以前に返されたすべての名前のファイルが存在する場合 **_mktemp**英字部分 'a' ~ 'z' の順序で、[次へ] の使用可能な英文字を置き換えることで、新しい名前を作成します。 たとえば場合、*基本*は。

> **fn**

によって提供される 5 桁の値と **_mktemp** 12345、返される最初の名前は。

> **fna12345**

この名前は FNA12345 ファイルを作成するために使用し、このファイルが存在する場合、[次へ] の名前が同じプロセスまたはスレッドで、同じ呼び出しで返されます*基本*の*nameTemplate*は。

> **fnb12345**

FNA12345 が存在しない場合、次に返される名前はもう一度次のようになります。

> **fna12345**

**_mktemp**の特定の組み合わせの 26 の一意のファイル名の最大値を作成できます*基本*と*nameTemplate*値。 FNZ12345 最後の一意のファイル名は、そのため、 **_mktemp**を作成することができます、*基本*と*nameTemplate*この例で使用される値。

失敗した場合、 **errno**が設定されています。 場合*nameTemplate*形式が無効です (6 個より少なくなるなど、X)、 **errno**に設定されている**EINVAL**です。 場合 **_mktemp** 26 のすべての可能なファイル名が既に存在するために一意の名前を作成することがない **_mktemp** nameTemplate を空の文字列に設定し、返します**EEXIST**です。

C++ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
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
