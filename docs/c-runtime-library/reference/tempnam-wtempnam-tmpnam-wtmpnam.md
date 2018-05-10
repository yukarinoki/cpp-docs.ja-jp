---
title: _tempnam、_wtempnam、tmpnam、_wtmpnam | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wtempnam
- _wtmpnam
- tmpnam
- _tempnam
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
- wtempnam
- _wtmpnam
- wtmpnam
- tmpnam
- _wtempnam
- _tempnam
dev_langs:
- C++
helpviewer_keywords:
- wtempnam function
- file names [C++], creating temporary
- _tempnam function
- ttmpnam function
- tmpnam function
- tempnam function
- wtmpnam function
- temporary files, creating
- file names [C++], temporary
- _ttmpnam function
- _wtmpnam function
- _wtempnam function
ms.assetid: 3ce75f0f-5e30-42a6-9791-8d7cbfe70fca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55ff069d72d68493eee524ea2f9c012d2fc7f534
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="tempnam-wtempnam-tmpnam-wtmpnam"></a>_tempnam、_wtempnam、tmpnam、_wtmpnam

一時ファイルの作成に使用できる名前を生成します。 これらの関数のセキュリティを強化したバージョンを使用できます。「[tmpnam_s、_wtmpnam_s](tmpnam-s-wtmpnam-s.md)」を参照してください。

## <a name="syntax"></a>構文

```C
char *_tempnam(
   const char *dir,
   const char *prefix
);
wchar_t *_wtempnam(
   const wchar_t *dir,
   const wchar_t *prefix
);
char *tmpnam(
   char *str
);
wchar_t *_wtmpnam(
   wchar_t *str
);
```

### <a name="parameters"></a>パラメーター

*prefix*<br/>
によって返された名前の前に付けられる文字列 **_tempnam**です。

*dir*<br/>
TMP 環境変数がない場合、または TMP が有効なディレクトリではない場合にファイル名で使用されるパス。

*str*<br/>
生成された名前を保持し、関数によって返される名前と同じになるポインター。 これは、生成された名前を保存する便利な方法です。

## <a name="return-value"></a>戻り値

生成されるファイル名へのポインターを返しますこれらの関数または**NULL**障害が発生した場合。 しようとすると、エラーが発生する可能性が複数の**TMP_MAX** (STDIO を参照してください。H) を使用した呼び出し**tmpnam**を使用する場合または **_tempnam** TMP 環境変数で指定された無効なディレクトリ名があると、 *dir*パラメーター。

> [!NOTE]
> によって返されるポインター **tmpnam**と **_wtmpnam**内部の静的バッファーをポイントします。 これらのポインターの割り当てを解除するために [free](free.md) を呼び出さないでください。 **空き**によって割り当てられたポインターに対して呼び出される必要がある **_tempnam**と **_wtempnam**です。

## <a name="remarks"></a>コメント

これらの各関数は、現在存在しないファイルの名前を返します。 **tmpnam**名を返します。 現在の作業ディレクトリ内で一意と **_tempnam**現在以外のディレクトリに一意の名前を生成することができます。 ファイル名の前に円記号が付いていてパス情報がない場合 (\fname21 など)、その名前は現在の作業ディレクトリに対して有効なので注意してください。

**Tmpnam**でこの生成されたファイル名を格納する*str*です。 場合*str*は**NULL**、し**tmpnam**内部の静的バッファーに、結果を残します。 したがって後続の呼び出しは、この値を破棄します。 によって生成された名前**tmpnam**プログラムで生成されたファイル名と後の最初の呼び出しで構成されています**tmpnam**、基本 32 の連続する番号のファイル拡張子 (.1 のどちらから**TMP_MAX** STDIO にします。H は 32,767) です。

**_tempnam**は、次の規則によって選択されたディレクトリの一意のファイル名を生成します。

- TMP 環境変数が定義され、有効なディレクトリ名に設定された場合は、TMP で指定したディレクトリに対して一意のファイル名が生成されます。

- TMP 環境変数が定義されていない場合、または存在しないディレクトリの名前に設定されている場合 **_tempnam**を使用して、 *dir*パラメーターとして一意の名前を生成するパス。

- TMP 環境変数が定義されていない場合、または存在しないディレクトリの名前に設定されている場合で、 *dir*か**NULL**が存在しない、ディレクトリの名前を設定または **_tempnam**一意の名前を生成する現在の作業ディレクトリを使用します。 現時点では場合、両方 TMP と*dir*が存在しないディレクトリの名前を指定、 **_tempnam**関数呼び出しは失敗します。

によって返される名前 **_tempnam**の連結になります*プレフィックス*とシーケンシャル番号が含まれ、指定したディレクトリの一意のファイル名の作成に結合します。 **_tempnam**拡張子を持たないファイル名が生成されます。 **_tempnam**使用[malloc](malloc.md) %filename; に領域を割り当てるプログラムは不要になったときにこの領域の解放を担当します。

**_tempnam**と**tmpnam** OEM コード ページに基づいてマルチバイト文字のシーケンスを認識し、必要に応じてハンドル マルチバイト文字の文字列の引数が、オペレーティング システムから自動的に取得します。 **_wtempnam**のワイド文字バージョンは、 **_tempnam**; 引数と戻り値の **_wtempnam**ワイド文字列です。 **_wtempnam**と **_tempnam**という点以外の動作は同じ **_wtempnam**マルチバイト文字の文字列を処理しません。 **_wtmpnam**のワイド文字バージョンは、 **tmpnam**; の引数と戻り値 **_wtmpnam**ワイド文字列です。 **_wtmpnam**と**tmpnam**という点以外の動作は同じ **_wtmpnam**マルチバイト文字の文字列を処理しません。

場合 **_DEBUG**と **_CRTDBG_MAP_ALLOC**定義すると、 **_tempnam**と **_wtempnam**への呼び出しによって置き換えられます[_tempnam_dbg と _wtempnam_dbg](tempnam-dbg-wtempnam-dbg.md)です。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttmpnam**|**tempnam**|**tempnam**|**_wtmpnam**|
|**_ttempnam**|**_tempnam**|**_tempnam**|**_wtempnam**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_tempnam**|\<stdio.h>|
|**_wtempnam**、 **_wtmpnam**|\<stdio.h> または \<wchar.h>|
|**tempnam**|\<stdio.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_tempnam.c
// compile with: /W3
// This program uses tmpnam to create a unique filename in the
// current working directory, then uses _tempnam to create
// a unique filename with a prefix of stq.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   char* name1 = NULL;
   char* name2 = NULL;

   // Create a temporary filename for the current working directory:
   if( ( name1 = tmpnam( NULL ) ) != NULL ) // C4996
   // Note: tmpnam is deprecated; consider using tmpnam_s instead
      printf( "%s is safe to use as a temporary file.\n", name1 );
   else
      printf( "Cannot create a unique filename\n" );

   // Create a temporary filename in temporary directory with the
   // prefix "stq". The actual destination directory may vary
   // depending on the state of the TMP environment variable and
   // the global variable P_tmpdir.

   if( ( name2 = _tempnam( "c:\\tmp", "stq" ) ) != NULL )
      printf( "%s is safe to use as a temporary file.\n", name2 );
   else
      printf( "Cannot create a unique filename\n" );

   // When name2 is no longer needed :
   if(name2)
     free(name2);

}
```

```Output
\s1gk. is safe to use as a temporary file.
C:\DOCUME~1\user\LOCALS~1\Temp\2\stq2 is safe to use as a temporary file.
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[malloc](malloc.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[tmpfile](tmpfile.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
