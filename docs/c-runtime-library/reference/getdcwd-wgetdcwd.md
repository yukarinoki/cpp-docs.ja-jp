---
title: _getdcwd、_wgetdcwd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _getdcwd
- _wgetdcwd
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
- wgetdcwd
- getdcwd
- _getdcwd
- tgetdcwd
- _wgetdcwd
- _tgetdcwd
dev_langs:
- C++
helpviewer_keywords:
- wgetdcwd function
- working directory
- getdcwd function
- _getdcwd function
- _wgetdcwd function
- current working directory
- directories [C++], current working
ms.assetid: 184152f5-c7b0-495b-918d-f9a6adc178bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b0ccc526b196982402ca3b795276df8c790ad35a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="getdcwd-wgetdcwd"></a>_getdcwd、_wgetdcwd

指定されたドライブの現在の作業ディレクトリの完全なパスを取得します。

## <a name="syntax"></a>構文

```C
char *_getdcwd(
   int drive,
   char *buffer,
   int maxlen
);
wchar_t *_wgetdcwd(
   int drive,
   wchar_t *buffer,
   int maxlen
);
```

### <a name="parameters"></a>パラメーター

*ドライブ*<br/>
ドライブを指定する負でない整数 (0 = 既定のドライブ、1 = A、2 = B など)。

指定されたドライブが使用できない場合、またはドライブの種類 (たとえば、リムーバブル ドライブ、固定ドライブ、CD-ROM ドライブ、RAM ディスク ドライブ、ネットワーク ドライブ) を特定できない場合、「 [Parameter Validation](../../c-runtime-library/parameter-validation.md)」に説明されているように、正しくないパラメーター ハンドラーが呼び出されます。

*バッファー*<br/>
パスの格納場所または **NULL**。

場合**NULL**を指定すると、この関数はバッファーを割り当てるには、少なくとも*maxlen*を使用してサイズ**malloc**、および戻り値の **_getdcwd**、割り当てられたバッファーへのポインターです。 バッファーを呼び出すことによって解放できます**空き**し、ポインターを渡します。

*maxlen*<br/>
文字数で、パスの最大長を指定する 0 以外正の整数: **char**の **_getdcwd**と**wchar_t**の **_wgetdcwd**.

場合*maxlen*ゼロより大きく、記載されている無効なパラメーター ハンドラーがない[パラメーターの検証](../../c-runtime-library/parameter-validation.md)が呼び出されます。

## <a name="return-value"></a>戻り値

指定したドライブ上の現在の作業ディレクトリの完全パスを表す文字列へのポインターまたは**NULL**エラーを示します。

場合*バッファー*として指定された**NULL**に割り当てる十分なメモリがあると*maxlen*文字で、エラーが発生し、 **errno**は設定**ENOMEM**です。 終端の null 文字を含むパスの長さを超えた場合*maxlen*、エラーが発生し、 **errno**に設定されている**ERANGE**です。 これらのエラー コードの詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>コメント

**_Getdcwd**関数は、指定したドライブ上の現在の作業ディレクトリの完全なパスを取得しに格納*バッファー*です。 現在の作業ディレクトリがルートに設定されている場合、文字列は円記号 (\\) で終わります。 現在の作業ディレクトリがルート以外のディレクトリに設定されている場合、文字列は、円記号ではなく、ディレクトリの名前で終わります。

**_wgetdcwd**のワイド文字バージョンは、 **_getdcwd**、およびその*バッファー*パラメーターと戻り値はワイド文字列です。 それ以外の場合、 **_wgetdcwd**と **_getdcwd**動作は同じです。

この関数は、スレッドセーフではない **GetFullPathName**に依存しますが、スレッドセーフです。 ただし、マルチスレッド アプリケーションでこの関数と **GetFullPathName**を両方とも呼び出した場合、スレッド セーフを侵害する可能性があります。 詳細については、[MSDN ライブラリ](http://go.microsoft.com/fwlink/p/?linkid=150542) にアクセスし、**GetFullPathName** を検索します。

この関数のバージョン、 **_nolock**サフィックス同じように動作するこの関数はスレッド セーフではありませんで他のスレッドによる干渉から保護されないという点を除いて。 詳細については、[_getdcwd_nolock、_wgetdcwd_nolock](getdcwd-nolock-wgetdcwd-nolock.md) を参照してください。

ときに **_DEBUG**と **_CRTDBG_MAP_ALLOC**への呼び出しで定義されている **_getdcwd**と **_wgetdcwd** への呼び出しによって置き換えられます **_getdcwd_dbg**と **_wgetdcwd_dbg**メモリ割り当てをデバッグできるようにします。 詳細については、[_getdcwd_dbg、_wgetdcwd_dbg](getdcwd-dbg-wgetdcwd-dbg.md) を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetdcwd**|**_getdcwd**|**_getdcwd**|**_wgetdcwd**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_getdcwd**|\<direct.h>|
|**_wgetdcwd**|\<direct.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

[_getdrive](getdrive.md) の例を参照してください。

## <a name="see-also"></a>関連項目

[ディレクトリ制御](../../c-runtime-library/directory-control.md)<br/>
[_chdir、_wchdir](chdir-wchdir.md)<br/>
[_getcwd、_wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdrive](getdrive.md)<br/>
[_mkdir、_wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir、_wrmdir](rmdir-wrmdir.md)<br/>
