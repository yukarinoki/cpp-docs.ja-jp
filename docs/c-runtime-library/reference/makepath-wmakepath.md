---
title: _makepath、_wmakepath
ms.date: 4/2/2020
api_name:
- _makepath
- _wmakepath
- _o__makepath
- _o__wmakepath
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wmakepath
- _tmakepath
- makepath
- tmakepath
- wmakepath
- _makepath
helpviewer_keywords:
- _makepath function
- wmakepath function
- makepath function
- _tmakepath function
- paths
- _wmakepath function
- tmakepath function
ms.assetid: 5930b197-a7b8-46eb-8519-2841a58cd026
ms.openlocfilehash: b92e056816183b4bbb07edb3efec4415655d655e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341594"
---
# <a name="_makepath-_wmakepath"></a>_makepath、_wmakepath

コンポーネントからパス名を作成します。 これらの関数のセキュリティを強化したバージョンについては、「[_makepath_s、_wmakepath_s (_makepath_s、_wmakepath_s)](makepath-s-wmakepath-s.md)」をご覧ください。

## <a name="syntax"></a>構文

```C
void _makepath(
   char *path,
   const char *drive,
   const char *dir,
   const char *fname,
   const char *ext
);
void _wmakepath(
   wchar_t *path,
   const wchar_t *drive,
   const wchar_t *dir,
   const wchar_t *fname,
   const wchar_t *ext
);
```

### <a name="parameters"></a>パラメーター

*path*<br/>
完全なパスのバッファー。

*ドライブ*<br/>
必要なドライブに対応する文字 (A、B など) と、この後に続くオプションのコロンを含んでいます。 **_makepath**は、コロンが存在しない場合は、自動的に複合パスに挿入されます。 *ドライブ*が**NULL**の場合、または空の文字列を指す場合、複合*パス*文字列にはドライブ文字は表示されません。

*Dir*<br/>
ドライブ指定子も実際のファイル名も含まない、ディレクトリのパスを含んでいます。 末尾のスラッシュは省略可能で、スラッシュ (/) または円記号 (\\) のいずれかまたは両方を単一*の dir*引数で使用できます。 末尾のスラッシュ (/ と \\ のいずれも) を指定していない場合は、スラッシュが自動的に挿入されます。 *dir*が**NULL の**場合、または空の文字列を指す場合、複合*パス*文字列にディレクトリ パスは挿入されません。

*Fname*<br/>
ファイル名拡張子がないベース ファイル名が含まれています。 *fname*が**NULL の**場合、または空の文字列を指す場合、複合*パス*文字列にファイル名は挿入されません。

*内線*<br/>
実際のファイル名拡張子が含まれており、先頭のピリオド (.) の有無は問いません。 **_makepath**は *、ext*に表示されない場合は、自動的に挿入されます。*ext*が**NULL の**場合、または空の文字列を指す場合、複合*パス*文字列に拡張子は挿入されません。

## <a name="remarks"></a>解説

**_makepath**関数は、個々のコンポーネントから複合パス文字列を作成し、結果を*path*に格納します。 *パス*には、ドライブ文字、ディレクトリ パス、ファイル名、およびファイル名拡張子が含まれる場合があります。 **_wmakepath**はワイド文字の **_makepath**です。**_wmakepath**の引数はワイド文字列です。 **_wmakepath**と **_makepath**は同じように動作します。

**セキュリティに関するメモ** null で終わる文字列を使用してください。 バッファ オーバーランを回避するには、null で終わる文字列が*パス*バッファのサイズを超えないようにする必要があります。 **_makepath**では、複合パス文字列の長さが **_MAX_PATH**を超えていないことを保証しません。 詳しくは、「 [バッファー オーバーランの回避](/windows/win32/SecBP/avoiding-buffer-overruns)」をご覧ください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath**|**_makepath**|**_makepath**|**_wmakepath**|

*path*引数は、完全なパスを保持するのに十分な大きさの空のバッファを指している必要があります。 複合*パス*は、Stdlib.h で定義されている **_MAX_PATH**定数より大きくすることはできません。

path が**NULL**の場合は、「パラメーター[の検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 さらに **、errno**は**EINVAL**に設定されます。 **NULL**値は、他のすべてのパラメーターに許可されます。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_makepath**|\<stdlib.h>|
|**_wmakepath**|\<stdlib.h> または \<wchar.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_makepath.c
#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char path_buffer[_MAX_PATH];
   char drive[_MAX_DRIVE];
   char dir[_MAX_DIR];
   char fname[_MAX_FNAME];
   char ext[_MAX_EXT];

   _makepath( path_buffer, "c", "\\sample\\crt\\", "makepath", "c" ); // C4996
   // Note: _makepath is deprecated; consider using _makepath_s instead
   printf( "Path created with _makepath: %s\n\n", path_buffer );
   _splitpath( path_buffer, drive, dir, fname, ext ); // C4996
   // Note: _splitpath is deprecated; consider using _splitpath_s instead
   printf( "Path extracted with _splitpath:\n" );
   printf( "   Drive: %s\n", drive );
   printf( "   Dir: %s\n", dir );
   printf( "   Filename: %s\n", fname );
   printf( "   Ext: %s\n", ext );
}
```

```Output
Path created with _makepath: c:\sample\crt\makepath.c

Path extracted with _splitpath:
   Drive: c:
   Dir: \sample\crt\
   Filename: makepath
   Ext: .c
```

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[_fullpath、_wfullpath](fullpath-wfullpath.md)<br/>
[_splitpath、_wsplitpath](splitpath-wsplitpath.md)<br/>
[_makepath_s、_wmakepath_s](makepath-s-wmakepath-s.md)<br/>
