---
title: _mktemp_s、_wmktemp_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mktemp_s
- _wmktemp_s
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
apitype: DLLExport
f1_keywords:
- wmktemp_s
- mktemp_s
- _mktemp_s
- _wmktemp_s
dev_langs:
- C++
helpviewer_keywords:
- _tmktemp_s function
- mktemp_s function
- _wmktemp_s function
- _mktemp_s function
- files [C++], temporary
- tmktemp_s function
- wmktemp_s function
- temporary files [C++]
ms.assetid: 92a7e269-7f3d-4c71-bad6-14bc827a451d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d0ed525f44150943496cddde57699035d8b62b6d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="mktemps-wmktemps"></a>_mktemp_s、_wmktemp_s

一意のファイル名を作成します。 これらは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_mktemp、_wmktemp](mktemp-wmktemp.md) です。

## <a name="syntax"></a>構文

```C
errno_t _mktemp_s(
   char *nameTemplate,
   size_t sizeInChars
);
errno_t _wmktemp_s(
   wchar_t *nameTemplate,
   size_t sizeInChars
);
template <size_t size>
errno_t _mktemp_s(
   char (&nameTemplate)[size]
); // C++ only
template <size_t size>
errno_t _wmktemp_s(
   wchar_t (&nameTemplate)[size]
); // C++ only
```

### <a name="parameters"></a>パラメーター

*nameTemplate*<br/>
ファイル名のパターン。

*sizeInChars*<br/>
シングル バイト文字で、バッファーのサイズ **_mktemp_s**以外の場合はワイド文字に **_wmktemp_s**、null 終端文字を含むです。

## <a name="return-value"></a>戻り値

これらの関数のどちらも、成功した場合は 0 を返し、エラーの場合はエラー コードを返します。

### <a name="error-conditions"></a>エラー条件

|*nameTemplate*|*sizeInChars*|戻り値|内の新しい値*nameTemplate*|
|----------------|-------------------|----------------------|-------------------------------|
|**NULL**|任意|**EINVAL**|**NULL**|
|形式が正しくありません (「解説」を参照してください正しい形式のセクション)。|任意|**EINVAL**|空の文字列|
|任意|X の数以下|**EINVAL**|空の文字列|

上記のいずれかのエラー条件が発生すると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 続けるには、実行が許可された場合**errno**に設定されている**EINVAL**関数を返しますと**EINVAL**です。

## <a name="remarks"></a>コメント

**_Mktemp_s**関数を変更することで一意のファイル名を作成、 *nameTemplate*引数、ように呼び出しの後、 *nameTemplate*ポインターが指す文字列新しいファイル名を含むです。 **_mktemp_s**マルチバイト文字の文字列引数には、実行時のシステムによって現在使用中のマルチバイト コード ページに基づいてマルチバイト文字シーケンスを認識することを必要に応じて自動的に処理します。 **_wmktemp_s**のワイド文字バージョンは、 **_mktemp_s**; の引数 **_wmktemp_s**ワイド文字列です。 **_wmktemp_s**と **_mktemp_s**点を除いてそれ以外の場合、動作は同じ **_wmktemp_s**マルチバイト文字の文字列を処理しません。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp_s**|**_mktemp_s**|**_mktemp_s**|**_wmktemp_s**|

*NameTemplate*引数が、フォーム**baseXXXXXX**ここで、*基本*が提供する、新しいファイル名の一部で各 X がで指定された文字のプレース ホルダー **_mktemp_s**です。 内の各プレース ホルダー文字*nameTemplate*大文字 X. をする必要があります **_mktemp_s**保持*基本*し、最初の後続の X を英字に置き換えます。 **_mktemp_s**末尾の次の置換 X、5 桁の値です。 この値は、プロセス、またはマルチ スレッド プログラムでは、呼び出し元のスレッド、呼び出し元を識別する一意の番号。

呼び出しが成功した **_mktemp_s**変更*nameTemplate*です。 各後続の呼び出し、同じプロセスまたはスレッドを同じ*nameTemplate*引数、 **_mktemp_s**によって返された名前に一致するファイル名の確認 **_mktemp_s**以前の呼び出しです。 指定した名前のファイルが存在しない場合 **_mktemp_s**その名前を返します。 以前に返されたすべての名前のファイルが存在する場合 **_mktemp_s**英字部分 'a' ~ 'z' の順序で、[次へ] の使用可能な英文字を置き換えることで、新しい名前を作成します。 たとえば場合、*基本*は。

> **fn**

によって提供される 5 桁の値と **_mktemp_s** 12345、返される最初の名前は。

> **fna12345**

この名前は FNA12345 ファイルを作成するために使用し、このファイルが存在する場合、[次へ] の名前が同じプロセスまたはスレッドで、同じ呼び出しで返されます*基本*の*nameTemplate*は。

> **fnb12345**

FNA12345 が存在しない場合、次に返される名前はもう一度次のようになります。

> **fna12345**

**_mktemp_s**の特定の組み合わせの 26 の一意のファイル名の最大値を作成できます*基本*と*nameTemplate*値。 FNZ12345 最後の一意のファイル名は、そのため、 **_mktemp_s**を作成することができます、*基本*と*nameTemplate*この例で使用される値。

C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_mktemp_s**|\<io.h>|
|**_wmktemp_s**|\<io.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```cpp
// crt_mktemp_s.cpp
/* The program uses _mktemp to create
* five unique filenames. It opens each filename
* to ensure that the next name is unique.
*/

#include <io.h>
#include <string.h>
#include <stdio.h>

char *fnTemplate = "fnXXXXXX";
char names[5][9];

int main()
{
   int i, err, sizeInChars;
   FILE *fp;

   for( i = 0; i < 5; i++ )
   {
      strcpy_s( names[i], sizeof(names[i]), fnTemplate );
      /* Get the size of the string and add one for the null terminator.*/
      sizeInChars = strnlen(names[i], 9) + 1;
      /* Attempt to find a unique filename: */
      err = _mktemp_s( names[i], sizeInChars );
      if( err != 0 )
         printf( "Problem creating the template" );
      else
      {
         if( fopen_s( &fp, names[i], "w" ) == 0 )
            printf( "Unique filename is %s\n", names[i] );
         else
            printf( "Cannot open %s\n", names[i] );
         fclose( fp );
      }
   }

   return 0;
}
```

### <a name="sample-output"></a>出力例

```Output
Unique filename is fna03188
Unique filename is fnb03188
Unique filename is fnc03188
Unique filename is fnd03188
Unique filename is fne03188
```

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[fopen、_wfopen](fopen-wfopen.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_getpid](getpid.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_tempnam、_wtempnam、tmpnam、_wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
