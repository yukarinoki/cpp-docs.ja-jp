---
title: _mktemp_s、_wmktemp_s
ms.date: 4/2/2020
api_name:
- _mktemp_s
- _wmktemp_s
- _o__mktemp_s
- _o__wmktemp_s
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
- wmktemp_s
- mktemp_s
- _mktemp_s
- _wmktemp_s
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
ms.openlocfilehash: 061c5647b2c5a5e79b017cf93989f62ad19cfc0a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338751"
---
# <a name="_mktemp_s-_wmktemp_s"></a>_mktemp_s、_wmktemp_s

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

*名前テンプレート*<br/>
ファイル名のパターン。

*サイズインチャーズ*<br/>
**_mktemp_s**の 1 バイト文字でのバッファーのサイズ。**_wmktemp_s**のワイド文字 (ヌル終端文字を含む)

## <a name="return-value"></a>戻り値

これらの関数のどちらも、成功した場合は 0 を返し、エラーの場合はエラー コードを返します。

### <a name="error-conditions"></a>エラー条件

|*名前テンプレート*|*サイズインチャーズ*|戻り値|名前の新しい値*テンプレート*|
|----------------|-------------------|----------------------|-------------------------------|
|**NULL**|any|**Einval**|**NULL**|
|形式が正しくありません (正しい形式については、「解説」を参照してください)|any|**Einval**|空の文字列|
|any|X の数以下|**Einval**|空の文字列|

上記のいずれかのエラー条件が発生すると、「[パラメータの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラ―が呼び出されます。 実行を続行できる場合 **、errno**は**EINVAL**に設定され、関数は**EINVAL**を返します。

## <a name="remarks"></a>解説

**_mktemp_s**関数は *、nameTemplate*引数を変更して一意のファイル名を作成し、呼び出し後に*nameTemplate*ポインターが新しいファイル名を含む文字列を指します。 **_mktemp_s**は、マルチバイト文字の文字列引数を適切に処理し、ランタイム システムで現在使用されているマルチバイト コード ページに従ってマルチバイト文字シーケンスを認識します。 **_wmktemp_s**はワイド文字の **_mktemp_s**です。**_wmktemp_s**の引数はワイド文字列です。 **_wmktemp_s**と **_mktemp_s**は **、_wmktemp_s**がマルチバイト文字文字列を処理しないことを除いて、他の方法で同様に動作します。

これらの関数のデバッグ ライブラリ バージョンは、まずバッファーに 0xFE を設定します。 この動作を無効にするには、[_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md) を使用します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp_s**|**_mktemp_s**|**_mktemp_s**|**_wmktemp_s**|

*nameTemplate*引数には**baseXXXXXX**という形式があり *、base*は指定した新しいファイル名の一部であり、各 X は **_mktemp_s**によって提供される文字のプレースホルダーです。 *nameTemplate*の各プレースホルダ文字は大文字の**X.** である必要_mktemp_s*ベース*を保持し、最初の末尾の X をアルファベット文字に置き換えます。 **_mktemp_s**は、後続の X を 5 桁の値に置き換えます。この値は、呼び出し元のプロセス、またはマルチスレッド・プログラムの呼び出しスレッドを識別する固有の番号です。

**_mktemp_s**への成功した呼び出しは *、名前を変更します。* 同じプロセスまたは同じスレッドからの同じ*nameTemplate*引数からの呼び出しでは **、_mktemp_s**以前の呼び出しで **_mktemp_s**によって返された名前と一致するファイル名をチェックします。 指定された名前のファイルが存在しない場合 **、_mktemp_s**はその名前を返します。 以前に返されたすべての名前にファイルが存在する場合 **、_mktemp_s**は、前に返された名前で使用した英字を、'a' から 'z' までの順に、次の使用可能な小文字に置き換えることによって、新しい名前を作成します。 たとえば、*ベース*が次の場合です。

> **Fn**

**_mktemp_s**によって提供される 5 桁の値は 12345 で、戻される最初の名前は次のようになります。

> **fna12345**

この名前を使用してファイル FNA12345 を作成しても、このファイルがまだ存在する場合、name の*同じベース*を持つ同じプロセスまたはスレッドからの呼び出しで返される次の名前は次のようになります*テンプレート:*

> **fnb12345**

FNA12345 が存在しない場合、次に返される名前はもう一度次のようになります。

> **fna12345**

**_mktemp_s、base**と*nameTemplate*の値の任意の組み*base*合わせに対して最大 26 個の一意のファイル名を作成できます。 したがって、FNZ12345 は、この例で使用 **_mktemp_s***基本*と*nameTemplate*値に対して作成できる最後の一意のファイル名です。

C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_mktemp_s**|\<io.h>|
|**_wmktemp_s**|\<io.h> または \<wchar.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

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

### <a name="sample-output"></a>サンプル出力

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
