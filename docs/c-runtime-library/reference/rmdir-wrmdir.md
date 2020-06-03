---
title: _rmdir、_wrmdir
ms.date: 4/2/2020
api_name:
- _wrmdir
- _rmdir
- _o__rmdir
- _o__wrmdir
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- trmdir
- _trmdir
- wrmdir
- _rmdir
- _wrmdir
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
ms.openlocfilehash: c0c5055a499614f364370b7aa90697898dc510ab
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82916924"
---
# <a name="_rmdir-_wrmdir"></a>_rmdir、_wrmdir

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

ディレクトリが正常に削除された場合、これらの関数はそれぞれ 0 を返します。 戻り値-1 はエラーを示し、 **errno**は次のいずれかの値に設定されます。

|errno の値|条件|
|-|-|
| **ENOTEMPTY** | 指定されたパスがディレクトリではないか、ディレクトリが空でない、またはディレクトリが現在の作業ディレクトリかルート ディレクトリのいずれかです。 |
| **ENOENT** | パスが無効です。 |
| **EACCES** | プログラムに、ディレクトリに対して開いているハンドルがあります。 |

リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**_Rmdir**関数は、 *dirname*によって指定されたディレクトリを削除します。 ディレクトリは空である必要があり、現在の作業ディレクトリまたはルート ディレクトリではないことが必要です。

**_wrmdir**は **_rmdir**のワイド文字バージョンです。**_wrmdir**の*dirname*引数は、ワイド文字列です。 **_wrmdir**と **_rmdir**は同じように動作します。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_trmdir**|**_rmdir**|**_rmdir**|**_wrmdir**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_rmdir**|\<direct.h>|
|**_wrmdir**|\<direct.h> または \<wchar.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

「[_mkdir](mkdir-wmkdir.md)」の例をご覧ください。

## <a name="see-also"></a>関連項目

[ディレクトリ制御](../../c-runtime-library/directory-control.md)<br/>
[_chdir、_wchdir](chdir-wchdir.md)<br/>
[_mkdir、_wmkdir](mkdir-wmkdir.md)<br/>
