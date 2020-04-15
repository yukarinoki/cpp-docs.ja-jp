---
title: _chdrive
ms.date: 4/2/2020
api_name:
- _chdrive
- _o__chdrive
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
- chdrive
- _chdrive
helpviewer_keywords:
- drives, changing
- _chdrive function
- chdrive function
ms.assetid: 212a1a4b-4fa8-444e-9677-7fca4c8c47e3
ms.openlocfilehash: 0c19fefcf6a766842ee2e25cbe6bdb61bbf48e7d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333344"
---
# <a name="_chdrive"></a>_chdrive

現在の作業ドライブを変更します。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int _chdrive(
   int drive
);
```

### <a name="parameters"></a>パラメーター

*ドライブ*<br/>
現在の作業ドライブを指定する 1 ～ 26 の整数 (1 = A、2 = B など)。

## <a name="return-value"></a>戻り値

現在の作業ドライブが正常に変更された場合はゼロ (0)、それ以外の場合は -1。

## <a name="remarks"></a>解説

*ドライブ*が 1 から 26 までの範囲にない場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」の説明に従って、無効なパラメーター ハンドラーが呼び出されます。 実行が続行できる場合 **、_chdrive**関数は -1 を返し **、errno**は**EACCES**に設定され **、_doserrno**は**ERROR_INVALID_DRIVE**に設定されます。

**_chdrive** 関数は、スレッド セーフではない **SetCurrentDirectory** 関数に依存するため、スレッド セーフではありません。 マルチスレッド アプリケーションで **_chdrive** を安全に使用するには、独自のスレッド同期を用意する必要があります。 詳細については、「[を参照してください。](/windows/win32/api/winbase/nf-winbase-setcurrentdirectory)

**_chdrive** 関数は現在の作業ドライブのみを変更します。**_chdir** は現在の作業ディレクトリを変更します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_chdrive**|\<direct.h>|

詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

[_getdrive](getdrive.md) の例を参照してください。

## <a name="see-also"></a>関連項目

[ディレクトリ制御](../../c-runtime-library/directory-control.md)<br/>
[_chdir、_wchdir](chdir-wchdir.md)<br/>
[_fullpath、_wfullpath](fullpath-wfullpath.md)<br/>
[_getcwd、_wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdrive](getdrive.md)<br/>
[_mkdir、_wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir、_wrmdir](rmdir-wrmdir.md)<br/>
[system、_wsystem](system-wsystem.md)<br/>
