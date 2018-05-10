---
title: _makepath_s、_wmakepath_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wmakepath_s
- _makepath_s
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wmakepath_s
- makepath_s
- _makepath_s
- wmakepath_s
dev_langs:
- C++
helpviewer_keywords:
- _makepath_s function
- wmakepath_s function
- paths
- _wmakepath_s function
- makepath_s function
ms.assetid: 4405e43c-3d63-4697-bb80-9b8dcd21d027
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a981e8758200e055693f24761238c98c3755311c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="makepaths-wmakepaths"></a>_makepath_s、_wmakepath_s

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

*sizeInWords*<br/>
バッファーのサイズ (単語単位)。

*sizeInBytes*<br/>
バッファーのサイズ (バイト単位)。

*ドライブ*<br/>
必要なドライブに対応する文字 (A、B など) と、省略可能である後続のコロンを含んでいます。 **_makepath_s**が存在しない場合、複合パスにコロンを自動的に挿入します。 場合*ドライブ*は**NULL** 、空の文字列へのポインター、ドライブ文字には表示されません複合または*パス*文字列。

*dir*<br/>
ドライブ指定子も実際のファイル名も含まない、ディレクトリのパスを含んでいます。 末尾のスラッシュは省略可能とスラッシュ (/) または円記号 (\\) 1 つの両方を使用する場合がありますまたは*dir*引数。 末尾のスラッシュ (/ と \\ のいずれも) を指定していない場合は、スラッシュが自動的に挿入されます。 場合*dir*は**NULL**複合でないディレクトリのパス、空の文字列へのポインターを挿入または*パス*文字列。

*fname*<br/>
ファイル名拡張子がないベース ファイル名が含まれています。 場合*fname*は**NULL**複合にないファイル名を空の文字列へのポインターが挿入または*パス*文字列。

*ext*<br/>
先行するピリオド (.) の有無を問わず、実際のファイル名拡張子が含まれています。 **_makepath_s**が表示されない場合は、期間を自動的に挿入します。 *ext*です。場合*ext*は**NULL**複合に拡張子がない、空の文字列へのポインターが挿入または*パス*文字列。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。

### <a name="error-conditions"></a>エラー条件

|*path*|*sizeInWords* / *sizeInBytes*|Return|内容*パス*|
|------------|------------------------------------|------------|------------------------|
|**NULL**|任意|**EINVAL**|変更されない|
|任意|<= 0|**EINVAL**|変更されない|

上記のいずれかのエラー条件が発生すると、これらの関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 続けるには、実行が許可された場合**errno**に設定されている**EINVAL**関数を返しますと**EINVAL**です。 **NULL**パラメーターは許可されて*ドライブ*、 *fname*、および*ext*です。これらのパラメーターが Null ポインターまたは空の文字列である場合の動作の詳細については、「コメント」セクションを参照してください。

## <a name="remarks"></a>コメント

**_Makepath_s**関数の結果を格納する、個々 のコンポーネントから複合パス文字列を作成する*パス*です。 *パス*ドライブ、ディレクトリのパス、ファイル名、およびファイル名拡張子を含めることがあります。 **_wmakepath_s**のワイド文字バージョンは、 **_makepath_s**; 引数 **_wmakepath_s**ワイド文字列です。 **_wmakepath_s**と **_makepath_s**それ以外の場合の動作は同じです。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath_s**|**_makepath_s**|**_makepath_s**|**_wmakepath_s**|

*パス*引数は、空の完全なパスを保持するのに十分な大きさのバッファーを指す必要があります。 複合*パス*以下にする必要があります、 **_MAX_PATH** Stdlib.h で定義された定数です。

パスが場合**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 さらに、 **errno**に設定されている**EINVAL**です。 **NULL**他のすべてのパラメーターの値が許可されます。

C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

これらの関数のデバッグ バージョンは、最初にバッファーを 0xFD で埋めます。 この動作を無効にするには、[_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).を使用します。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_makepath_s**|\<stdlib.h>|
|**_wmakepath_s**|\<stdlib.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
