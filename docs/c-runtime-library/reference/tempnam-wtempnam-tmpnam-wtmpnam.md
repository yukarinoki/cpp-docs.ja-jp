---
title: _tempnam、_wtempnam、tmpnam、_wtmpnam
ms.date: 11/04/2016
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
ms.openlocfilehash: 29fa8fc836b1b52bcf66247b3f6aaba47b8c2eaa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506796"
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
によって返された名前を付けたとなる文字列 **_tempnam**します。

*dir*<br/>
TMP 環境変数がない場合、または TMP が有効なディレクトリではない場合にファイル名で使用されるパス。

*str*<br/>
生成された名前を保持し、関数によって返される名前と同じになるポインター。 これは、生成された名前を保存する便利な方法です。

## <a name="return-value"></a>戻り値

これらの各関数の生成された名前にポインターを返しますまたは**NULL**障害が発生した場合。 しようとすると、エラーが発生する可能性が複数の**TMP_MAX** (STDIO を参照してください。H) 呼び出し**tmpnam**を使用する場合または **_tempnam** TMP 環境変数および指定されている、無効なディレクトリ名があると、 *dir*パラメーター。

> [!NOTE]
> によって返されるポインター **tmpnam**と **_wtmpnam**内部の静的バッファーをポイントします。 これらのポインターの割り当てを解除するために [free](free.md) を呼び出さないでください。 **無料**によって割り当てられたポインターに対して呼び出される必要がある **_tempnam**と **_wtempnam**します。

## <a name="remarks"></a>Remarks

これらの各関数は、現在存在しないファイルの名前を返します。 **tmpnam**によって返される指定された Windows 一時ディレクトリ内で一意の名前を返します[GetTempPathW](/windows/desktop/api/fileapi/nf-fileapi-gettemppathw)します。 **\_tempnam**以外は、指定された 1 つのディレクトリの一意の名前を生成します。 ファイル名の前に円記号が付いていてパス情報がない場合 (\fname21 など)、その名前は現在の作業ディレクトリに対して有効なので注意してください。

**Tmpnam**では、この生成されたファイル名を格納する*str*します。 場合*str*は**NULL**、し**tmpnam**内部の静的バッファーに結果を残します。 したがって後続の呼び出しは、この値を破棄します。 によって生成された名前**tmpnam**プログラムで生成されたファイル名と最初の呼び出し後**tmpnam**、base 32 で連番のファイル拡張子 (場合に、.1-.vvu **TMP_MAX** STDIO でします。H は 32,767 文字です)。

**_tempnam**次の規則によって選択されたディレクトリの一意のファイル名が生成されます。

- TMP 環境変数が定義され、有効なディレクトリ名に設定された場合は、TMP で指定したディレクトリに対して一意のファイル名が生成されます。

- TMP 環境変数が定義されていない場合、または存在しないディレクトリの名前に設定されている場合 **_tempnam**を使用して、 *dir*パラメーターとして一意の名前を生成するパス。

- TMP 環境変数が定義されていない場合、または存在しないディレクトリの名前に設定されている場合で、 *dir*か**NULL**が存在しないディレクトリの名前を設定または **_tempnam**現在の作業ディレクトリを使用して一意の名前を生成します。 現時点では場合、両方 TMP と*dir*が存在しないディレクトリの名前を指定、 **_tempnam**関数呼び出しは失敗します。

によって返される名前 **_tempnam**を連結したものになります*プレフィックス*とシーケンシャル番号が含まれ、指定したディレクトリの一意のファイル名を作成する結合されます。 **_tempnam**拡張機能を持たないファイル名が生成されます。 **_tempnam**使用[malloc](malloc.md) %filename; に領域を割り当てる、プログラムが不要になったときに、この領域を解放する責任を負います。

**_tempnam**と**tmpnam** OEM コード ページに従ってマルチバイト文字シーケンスを認識し、必要に応じてハンドル マルチバイト文字の文字列の引数が、オペレーティング システムから自動的に取得します。 **_wtempnam**のワイド文字バージョンは、 **_tempnam**; 引数と戻り値の **_wtempnam**はワイド文字列です。 **_wtempnam**と **_tempnam**動作は同じことを除いて **_wtempnam**マルチバイト文字の文字列を処理しません。 **_wtmpnam**のワイド文字バージョンは、 **tmpnam**; の引数と戻り値 **_wtmpnam**はワイド文字列です。 **_wtmpnam**と**tmpnam**動作は同じことを除いて **_wtmpnam**マルチバイト文字の文字列を処理しません。

場合 **_DEBUG**と **_CRTDBG_MAP_ALLOC**が定義されている、 **_tempnam**と **_wtempnam**呼び出しに置き換え[_tempnam_dbg と _wtempnam_dbg](tempnam-dbg-wtempnam-dbg.md)します。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttmpnam**|**tempnam**|**tempnam**|**_wtmpnam**|
|**_ttempnam**|**_tempnam**|**_tempnam**|**_wtempnam**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
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
// temporary directory, and _tempname to create a unique filename
// in C:\\tmp.

#include <stdio.h>
#include <stdlib.h>

int main(void)
{
   char * name1 = NULL;
   char * name2 = NULL;
   char * name3 = NULL;

   // Create a temporary filename for the current working directory:
   if ((name1 = tmpnam(NULL)) != NULL) { // C4996
   // Note: tmpnam is deprecated; consider using tmpnam_s instead
      printf("%s is safe to use as a temporary file.\n", name1);
   } else {
      printf("Cannot create a unique filename\n");
   }

   // Create a temporary filename in temporary directory with the
   // prefix "stq". The actual destination directory may vary
   // depending on the state of the TMP environment variable and
   // the global variable P_tmpdir.

   if ((name2 = _tempnam("c:\\tmp", "stq")) != NULL) {
      printf("%s is safe to use as a temporary file.\n", name2);
   } else {
      printf("Cannot create a unique filename\n");
   }

   // When name2 is no longer needed:
   if (name2) {
      free(name2);
   }

   // Unset TMP environment variable, then create a temporary filename in C:\tmp.
   if (_putenv("TMP=") != 0) {
      printf("Could not remove TMP environment variable.\n");
   }

   // With TMP unset, we will use C:\tmp as the temporary directory.
   // Create a temporary filename in C:\tmp with prefix "stq".
   if ((name3 = _tempnam("c:\\tmp", "stq")) != NULL) {
      printf("%s is safe to use as a temporary file.\n", name3);
   }
   else {
      printf("Cannot create a unique filename\n");
   }

   // When name3 is no longer needed:
   if (name3) {
      free(name3);
   }

   return 0;
}
```

```Output
C:\Users\LocalUser\AppData\Local\Temp\sriw.0 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\stq2 is safe to use as a temporary file.
c:\tmp\stq3 is safe to use as a temporary file.
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[malloc](malloc.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[tmpfile](tmpfile.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
