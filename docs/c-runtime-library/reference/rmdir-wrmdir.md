---
title: _rmdir、_wrmdir | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wrmdir
- _rmdir
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
- trmdir
- _trmdir
- wrmdir
- _rmdir
- _wrmdir
dev_langs:
- C++
helpviewer_keywords:
- _rmdir function
- directories [C++], deleting
- rmdir function
- directories [C++], removing
- trmdir function
- _trmdir function
- _wrmdir function
- wrmdir function
ms.assetid: 652c2a5a-b0ac-4493-864e-1edf484333c5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11e6521060932bd1273b6a3888332ac2c8b2bb7b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32406990"
---
# <a name="rmdir-wrmdir"></a>_rmdir、_wrmdir

ディレクトリを削除します。

## <a name="syntax"></a>構文

```C
int _rmdir(
   const char *dirname
);
int _wrmdir(
   const wchar_t *dirname
);
```

### <a name="parameters"></a>パラメーター

*dirname*<br/>
削除されるディレクトリのパス。

## <a name="return-value"></a>戻り値

ディレクトリが正常に削除された場合、これらの関数はそれぞれ 0 を返します。 戻り値-1 はエラーを示すと**errno**は、次の値のいずれかに設定します。

|errno の値|条件|
|-|-|
**ENOTEMPTY**|指定されたパスがディレクトリではないか、ディレクトリが空でない、またはディレクトリが現在の作業ディレクトリかルート ディレクトリのいずれかです。
**ENOENT**|パスが無効です。
**EACCES**|プログラムに、ディレクトリに対して開いているハンドルがあります。

リターン コードの詳細については、「 [_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>コメント

**_Rmdir**関数で指定されたディレクトリを削除する*dirname*です。 ディレクトリは空である必要があり、現在の作業ディレクトリまたはルート ディレクトリではないことが必要です。

**_wrmdir**のワイド文字バージョンは、 **_rmdir**; *dirname*に渡す引数 **_wrmdir**ワイド文字列です。 **_wrmdir**と **_rmdir**それ以外の場合の動作は同じです。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_trmdir**|**_rmdir**|**_rmdir**|**_wrmdir**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_rmdir**|\<direct.h>|
|**_wrmdir**|\<direct.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

「[_mkdir](mkdir-wmkdir.md)」の例をご覧ください。

## <a name="see-also"></a>関連項目

[ディレクトリ制御](../../c-runtime-library/directory-control.md)<br/>
[_chdir、_wchdir](chdir-wchdir.md)<br/>
[_mkdir、_wmkdir](mkdir-wmkdir.md)<br/>
