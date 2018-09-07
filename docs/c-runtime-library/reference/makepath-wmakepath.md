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
ms.openlocfilehash: 21cfcfb8a1c82fb351b85b0fb169a94dd3c2c5d4
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105095"
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

*path*<br/>
完全なパスのバッファー。

*ドライブ*<br/>
必要なドライブに対応する文字 (A、B など) と、省略可能である後続のコロンを含んでいます。 **_makepath**が存在しない場合、複合パスのコロンを自動的に挿入します。 場合*ドライブ*は**NULL**または空の文字列へのポインター、ドライブ文字は表示されません、合成*パス*文字列。

*dir*<br/>
ドライブ指定子も実際のファイル名も含まない、ディレクトリのパスを含んでいます。 末尾のスラッシュは省略可能なとフォワード スラッシュ (/) または円記号 (\\) 1 つの両方を使用する場合がありますまたは*dir*引数。 末尾のスラッシュ (/ と \\ のいずれも) を指定していない場合は、スラッシュが自動的に挿入されます。 場合*dir*は**NULL**または空の文字列でないディレクトリ パスへのポインターは、合成挿入*パス*文字列。

*fname*<br/>
ファイル名拡張子がないベース ファイル名が含まれています。 場合*fname*は**NULL**または空の文字列でないファイル名へのポインターは、合成挿入*パス*文字列。

*ext*<br/>
先行するピリオド (.) の有無を問わず、実際のファイル名拡張子が含まれています。 **_makepath**が表示されない場合、期間を自動的に挿入*ext*します。場合*ext*は**NULL**または拡張子のない空の文字列の指すは、合成挿入*パス*文字列。

## <a name="remarks"></a>Remarks

**_Makepath**関数の結果を格納する個別のコンポーネントから合成パス文字列を作成する*パス*します。 *パス*ドライブ文字、ディレクトリのパス、ファイル名、およびファイル名拡張子を含めることができます。 **_wmakepath**のワイド文字バージョンは、 **_makepath**; 引数 **_wmakepath**はワイド文字列です。 **_wmakepath**と **_makepath**動作は同じです。

**セキュリティに関するメモ** null で終わる文字列をご使用ください。 バッファー オーバーランを防ぐためには、null で終わる文字列を超えないのサイズ、*パス*バッファー。 **_makepath**合成パス文字列の長さを超えていないことを確認していない **_MAX_PATH**します。 詳しくは、「 [バッファー オーバーランの回避](/windows/desktop/SecBP/avoiding-buffer-overruns)」をご覧ください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath**|**_makepath**|**_makepath**|**_wmakepath**|

*パス*引数は、空の完全なパスを保持するために十分な大きさのバッファーを指す必要があります。 複合*パス*を超える必要があります、 **_MAX_PATH** Stdlib.h で定義されている定数。

パスがある場合**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 さらに、 **errno**に設定されている**EINVAL**します。 **NULL**他のすべてのパラメーター値を使用できます。

## <a name="requirements"></a>要件

|ルーチンによって返される値|必須ヘッダー|
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
