---
title: _makepath、_wmakepath | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _makepath
- _wmakepath
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
- _wmakepath
- _tmakepath
- makepath
- tmakepath
- wmakepath
- _makepath
dev_langs:
- C++
helpviewer_keywords:
- _makepath function
- wmakepath function
- makepath function
- _tmakepath function
- paths
- _wmakepath function
- tmakepath function
ms.assetid: 5930b197-a7b8-46eb-8519-2841a58cd026
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c339ce6ad67186dc7a4f43d7006c5beb047c8f90
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32404953"
---
# <a name="makepath-wmakepath"></a>_makepath、_wmakepath

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

*パス*完全パスのバッファー。

*ドライブ*アルファベット (A、B、およびなど) が含まれています、必要なドライブとオプションの後に続くコロンに対応します。 **_makepath**が存在しない場合、複合パスにコロンを自動的に挿入します。 場合*ドライブ*は**NULL** 、空の文字列へのポインター、ドライブ文字には表示されません複合または*パス*文字列。

*dir*ドライブ指定子または実際のファイルの名前を除いて、ディレクトリのパスが含まれています。 末尾のスラッシュは省略可能とスラッシュ (/) または円記号 (\\) 1 つの両方を使用する場合がありますまたは*dir*引数。 末尾のスラッシュ (/ と \\ のいずれも) を指定していない場合は、スラッシュが自動的に挿入されます。 場合*dir*は**NULL**複合でないディレクトリのパス、空の文字列へのポインターを挿入または*パス*文字列。

*fname*ファイル名拡張子を付けず基本ファイル名が含まれています。 場合*fname*は**NULL**複合にないファイル名を空の文字列へのポインターが挿入または*パス*文字列。

*ext*先頭にピリオド (.) の有無、実際のファイル名拡張子が含まれています。 **_makepath**が表示されない場合は、期間を自動的に挿入します。 *ext*です。場合*ext*は**NULL**複合に拡張子がない、空の文字列へのポインターが挿入または*パス*文字列。

## <a name="remarks"></a>コメント

**_Makepath**関数の結果を格納する、個々 のコンポーネントから複合パス文字列を作成する*パス*です。 *パス*ドライブ、ディレクトリのパス、ファイル名、およびファイル名拡張子を含めることがあります。 **_wmakepath**のワイド文字バージョンは、 **_makepath**; 引数 **_wmakepath**ワイド文字列です。 **_wmakepath**と **_makepath**それ以外の場合の動作は同じです。

**セキュリティに関するメモ** null で終わる文字列をご使用ください。 バッファー オーバーランを防ぐためには、null で終わる文字列を超えないのサイズ、*パス*バッファー。 **_makepath**複合パス文字列の長さを超えていないことを確認しません **_MAX_PATH**です。 詳しくは、「 [バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath**|**_makepath**|**_makepath**|**_wmakepath**|

*パス*引数は、空の完全なパスを保持するのに十分な大きさのバッファーを指す必要があります。 複合*パス*以下にする必要があります、 **_MAX_PATH** Stdlib.h で定義された定数です。

パスが場合**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 さらに、 **errno**に設定されている**EINVAL**です。 **NULL**他のすべてのパラメーターの値が許可されます。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_makepath**|\<stdlib.h>|
|**_wmakepath**|\<stdlib.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
