---
title: _getdcwd、_wgetdcwd
ms.date: 4/2/2020
api_name:
- _getdcwd
- _wgetdcwd
- _o__getdcwd
- _o__wgetdcwd
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wgetdcwd
- getdcwd
- _getdcwd
- tgetdcwd
- _wgetdcwd
- _tgetdcwd
helpviewer_keywords:
- wgetdcwd function
- working directory
- getdcwd function
- _getdcwd function
- _wgetdcwd function
- current working directory
- directories [C++], current working
ms.assetid: 184152f5-c7b0-495b-918d-f9a6adc178bd
ms.openlocfilehash: 3a4ca8ff3f1153893282c65bc4c2becd687138ce
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344395"
---
# <a name="_getdcwd-_wgetdcwd"></a>_getdcwd、_wgetdcwd

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

指定されたドライブが使用できない場合、またはドライブの種類 (リムーバブル、固定、CD-ROM、RAM ディスク、ネットワーク ドライブなど) が特定できない場合は、無効なパラメータ ハンドラが呼び出されます。 詳細については、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」を参照してください。

*バッファー*<br/>
パスの格納場所または **NULL**。

**NULL**を指定した場合、この関数は**malloc**を使用して少なくとも*最大*サイズ **_getdcwd**のバッファーを割り当てます。 バッファーは **、free**を呼び出してポインターを渡すことによって解放できます。

*Maxlen*<br/>
パスの最大長を文字で指定する 0 以外の正の整数**char**です **_wgetdcwd** **wchar_t** **_getdcwd。**

*maxlen*がゼロ以下の場合は、無効なパラメーター ハンドラーが呼び出されます。 詳細については、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」を参照してください。

## <a name="return-value"></a>戻り値

指定されたドライブ上の現在の作業ディレクトリの完全パスを表す文字列への**ポインター。**

*buffer*が**NULL**として指定され、メモリ不足のため*maxlen*文字を割り当てなかった場合は、エラーが発生し **、errno**が**ENOMEM**に設定されます。 終端の NULL 文字を含むパスの長さが*maxlen*を超えると、エラーが発生し **、errno**が**ERANGE**に設定されます。 これらのエラー コードの詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**_getdcwd**関数は、指定されたドライブ上の現在の作業ディレクトリの完全パスを取得し *、buffer*に格納します。 現在の作業ディレクトリがルートに設定されている場合、文字列は円記号 (\\) で終わります。 現在の作業ディレクトリがルート以外のディレクトリに設定されている場合、文字列は、円記号ではなく、ディレクトリの名前で終わります。

**_wgetdcwd**はワイド文字の **_getdcwd**のバージョンで、*バッファー*パラメーターと戻り値はワイド文字列です。 それ以外**の場合、_wgetdcwd**と **_getdcwd**は同じように動作します。

この関数は、スレッドセーフではない **GetFullPathName**に依存しますが、スレッドセーフです。 ただし、マルチスレッド アプリケーションでこの関数と [GetFullPathName](/windows/win32/api/fileapi/nf-fileapi-getfullpathnamew)を両方とも呼び出した場合、スレッド セーフを侵害する可能性があります。

**_nolock**サフィックスを持つこの関数のバージョンは、スレッド セーフではなく、他のスレッドによる干渉から保護されない点を除いて、この関数と同じように動作します。 詳細については、「 [_getdcwd_nolock, _wgetdcwd_nolock](getdcwd-nolock-wgetdcwd-nolock.md)」を参照してください。

**_DEBUG**と **_CRTDBG_MAP_ALLOC**が定義されている場合 **、_getdcwd**および **_wgetdcwd**の呼び出しは、メモリ割り当てをデバッグできるように **、_getdcwd_dbg**および **_wgetdcwd_dbg**の呼び出しに置き換えられます。 詳しくは[_getdcwd_dbg, _wgetdcwd_dbg](getdcwd-dbg-wgetdcwd-dbg.md)をご覧ください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetdcwd**|**_getdcwd**|**_getdcwd**|**_wgetdcwd**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_getdcwd**|\<direct.h>|
|**_wgetdcwd**|\<direct.h> または \<wchar.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

[_getdrive](getdrive.md)の例をご覧ください。

## <a name="see-also"></a>関連項目

[ディレクトリ制御](../../c-runtime-library/directory-control.md)<br/>
[_chdir、_wchdir](chdir-wchdir.md)<br/>
[_getcwd、_wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdrive](getdrive.md)<br/>
[_mkdir、_wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir、_wrmdir](rmdir-wrmdir.md)<br/>
