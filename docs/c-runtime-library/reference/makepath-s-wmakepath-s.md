---
title: _makepath_s、_wmakepath_s
ms.date: 4/2/2020
api_name:
- _wmakepath_s
- _makepath_s
- _o__makepath_s
- _o__wmakepath_s
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wmakepath_s
- makepath_s
- _makepath_s
- wmakepath_s
helpviewer_keywords:
- _makepath_s function
- wmakepath_s function
- paths
- _wmakepath_s function
- makepath_s function
ms.assetid: 4405e43c-3d63-4697-bb80-9b8dcd21d027
ms.openlocfilehash: 3a44651cb9ff8be806c45c6b6c5f41f810319a85
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341603"
---
# <a name="_makepath_s-_wmakepath_s"></a>_makepath_s、_wmakepath_s

コンポーネントからパス名を作成します。 これらは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_makepath、_wmakepath](makepath-wmakepath.md) です。

## <a name="syntax"></a>構文

```C
errno_t _makepath_s(
   char *path,
   size_t sizeInBytes,
   const char *drive,
   const char *dir,
   const char *fname,
   const char *ext
);
errno_t _wmakepath_s(
   wchar_t *path,
   size_t sizeInWords,
   const wchar_t *drive,
   const wchar_t *dir,
   const wchar_t *fname,
   const wchar_t *ext
);
template <size_t size>
errno_t _makepath_s(
   char (&path)[size],
   const char *drive,
   const char *dir,
   const char *fname,
   const char *ext
); // C++ only
template <size_t size>
errno_t _wmakepath_s(
   wchar_t (&path)[size],
   const wchar_t *drive,
   const wchar_t *dir,
   const wchar_t *fname,
   const wchar_t *ext
); // C++ only
```

### <a name="parameters"></a>パラメーター

*path*<br/>
完全なパスのバッファー。

*サイズインワーズ*<br/>
バッファーのサイズ (単語単位)。

*sizeInBytes*<br/>
バッファーのサイズ (バイト単位)。

*ドライブ*<br/>
必要なドライブに対応する文字 (A、B など) と、この後に続くオプションのコロンを含んでいます。 **_makepath_s**は、コロンが存在しない場合は、自動的に複合パスに挿入されます。 *ドライブ*が**NULL**の場合、または空の文字列を指す場合、複合*パス*文字列にはドライブ文字は表示されません。

*Dir*<br/>
ドライブ指定子も実際のファイル名も含まない、ディレクトリのパスを含んでいます。 末尾のスラッシュは省略可能で、スラッシュ (/) または円記号 (\\) のいずれかまたは両方を単一*の dir*引数で使用できます。 末尾のスラッシュ (/ と \\ のいずれも) を指定していない場合は、スラッシュが自動的に挿入されます。 *dir*が**NULL の**場合、または空の文字列を指す場合、複合*パス*文字列にディレクトリ パスは挿入されません。

*Fname*<br/>
ファイル名拡張子がないベース ファイル名が含まれています。 *fname*が**NULL の**場合、または空の文字列を指す場合、複合*パス*文字列にファイル名は挿入されません。

*内線*<br/>
実際のファイル名拡張子が含まれており、先頭のピリオド (.) の有無は問いません。 **_makepath_s**は *、ext*に表示されない場合は、自動的にピリオドを挿入します。*ext*が**NULL の**場合、または空の文字列を指す場合、複合*パス*文字列に拡張子は挿入されません。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。

### <a name="error-conditions"></a>エラー条件

|*path*|*サイズインワード* / *サイズインバイト数*|戻り値|*パス*の内容|
|------------|------------------------------------|------------|------------------------|
|**NULL**|any|**Einval**|変更されない|
|any|<= 0|**Einval**|変更されない|

上記のいずれかのエラー条件が発生すると、これらの関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行を続行できる場合 **、errno**は**EINVAL**に設定され、関数は**EINVAL**を返します。 **パラメータ***ドライブ**、fname*、および*ext*には NULL を使用できます。これらのパラメーターが null ポインターまたは空の文字列である場合の動作については、「解説」を参照してください。

## <a name="remarks"></a>解説

**_makepath_s**関数は、個々のコンポーネントから複合パス文字列を作成し、結果を*path*に格納します。 *パス*には、ドライブ文字、ディレクトリ パス、ファイル名、およびファイル名拡張子が含まれる場合があります。 **_wmakepath_s**は **、_makepath_s**のワイド文字バージョンです。**_wmakepath_s**の引数はワイド文字列です。 **_wmakepath_s**と **_makepath_s**は同じように動作します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath_s**|**_makepath_s**|**_makepath_s**|**_wmakepath_s**|

*path*引数は、完全なパスを保持するのに十分な大きさの空のバッファを指している必要があります。 複合*パス*は、Stdlib.h で定義されている **_MAX_PATH**定数より大きくすることはできません。

path が**NULL**の場合は、「パラメーター[の検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 さらに **、errno**は**EINVAL**に設定されます。 **NULL**値は、他のすべてのパラメーターに許可されます。

C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

これらの関数のデバッグ ライブラリ バージョンは、まずバッファーに 0xFE を設定します。 この動作を無効にするには、[_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md) を使用します。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_makepath_s**|\<stdlib.h>|
|**_wmakepath_s**|\<stdlib.h> または \<wchar.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_makepath_s.c

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char path_buffer[_MAX_PATH];
   char drive[_MAX_DRIVE];
   char dir[_MAX_DIR];
   char fname[_MAX_FNAME];
   char ext[_MAX_EXT];
   errno_t err;

   err = _makepath_s( path_buffer, _MAX_PATH, "c", "\\sample\\crt\\",
                      "crt_makepath_s", "c" );
   if (err != 0)
   {
      printf("Error creating path. Error code %d.\n", err);
      exit(1);
   }
   printf( "Path created with _makepath_s: %s\n\n", path_buffer );
   err = _splitpath_s( path_buffer, drive, _MAX_DRIVE, dir, _MAX_DIR, fname,
                       _MAX_FNAME, ext, _MAX_EXT );
   if (err != 0)
   {
      printf("Error splitting the path. Error code %d.\n", err);
      exit(1);
   }
   printf( "Path extracted with _splitpath_s:\n" );
   printf( "   Drive: %s\n", drive );
   printf( "   Dir: %s\n", dir );
   printf( "   Filename: %s\n", fname );
   printf( "   Ext: %s\n", ext );
}
```

```Output
Path created with _makepath_s: c:\sample\crt\crt_makepath_s.c

Path extracted with _splitpath_s:
   Drive: c:
   Dir: \sample\crt\
   Filename: crt_makepath_s
   Ext: .c
```

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[_fullpath、_wfullpath](fullpath-wfullpath.md)<br/>
[_splitpath_s、_wsplitpath_s](splitpath-s-wsplitpath-s.md)<br/>
[_makepath、_wmakepath](makepath-wmakepath.md)<br/>
