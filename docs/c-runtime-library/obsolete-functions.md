---
title: 古い関数
description: 廃止され、Microsoft C ランタイム ライブラリ (CRT) から削除された、廃止された関数の一覧を示します。
ms.date: 4/2/2020
api_name:
- _beep
- _sleep
- _loaddll
- _getdllprocaddr
- _seterrormode
- is_wctype
- _getsystime
- _setsystime
- _unloaddll
- _o__beep
- _o__getdllprocaddr
- _o__getsystime
- _o__loaddll
- _o__seterrormode
- _o__setsystime
- _o__sleep
- _o__unloaddll
- _o_is_wctype
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
- api-ms-win-crt-process-l1-1-0.dll
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-time-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- is_wctype
- _loaddll
- _unloaddll
- _getdllprocaddr
- _seterrormode
- _beep
- _sleep
- _getsystime
- corecrt_wctype/is_wctype
- process/_loaddll
- process/_unloaddll
- process/_getdllprocaddr
- stdlib/_seterrormode
- stdlib/_beep
- stdlib/_sleep
- time/_getsystime
- time/_setsystime
helpviewer_keywords:
- obsolete functions
- _beep function
- _sleep function
- _seterrormode function
ms.assetid: 8e14c2d4-1481-4240-8586-47eb43db02b0
ms.openlocfilehash: 5c3ebd9ff3533439cde2f1b46d100976b18e02c9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350995"
---
# <a name="obsolete-functions"></a>廃止された関数

ライブラリの機能の中には古くなって、新しい同等物で置き換えられているものがあります。 これらの関数を更新版に変更することをお勧めします。 他の古くなった関数は CRT から削除されています。 この資料では、廃止された関数と、Visual Studio の特定のバージョンで削除された関数を一覧表示します。

## <a name="deprecated-as-obsolete-in-visual-studio-2015"></a>Visual Studio 2015 で非推奨とされるため使用されていない

|古い関数|代替手段|
|-----------------------|-----------------|
|`is_wctype`|[iswctype](../c-runtime-library/reference/isctype-iswctype-isctype-l-iswctype-l.md)|
|`_loaddll`|[LoadLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw)、 [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)、または [LoadPackagedLibrary](/windows/win32/api/winbase/nf-winbase-loadpackagedlibrary)|
|`_unloaddll`|[FreeLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-freelibrary)|
|`_getdllprocaddr`|[GetProcAddress](../build/getprocaddress.md)|
|`_seterrormode`|[エラーモードを設定します。](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode)|
|`_beep`|[Beep](/windows/win32/api/utilapiset/nf-utilapiset-beep)|
|`_sleep`|[Sleep](/windows/win32/api/synchapi/nf-synchapi-sleep)|
|`_getsystime`|[GetLocalTime](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getlocaltime)|
|`_setsystime`|[SetLocalTime](/windows/win32/api/sysinfoapi/nf-sysinfoapi-setlocaltime)|

## <a name="removed-from-the-crt-in-visual-studio-2015"></a>Visual Studio 2015 では CRT から削除

|古い関数|代替手段|
|-----------------------|-----------------|
|[_cgets、_cgetws](../c-runtime-library/cgets-cgetws.md)|[_cgets_s、_cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md)|
|[取得, _getws](../c-runtime-library/gets-getws.md)|[gets_s、_getws_s](../c-runtime-library/reference/gets-s-getws-s.md)|
|[_get_output_format](../c-runtime-library/get-output-format.md)|なし|
|[_heapadd](../c-runtime-library/heapadd.md)|なし|
|[_heapset](../c-runtime-library/heapset.md)|なし|
|[inp, inpw, _inp, _inpw, _inpd](../c-runtime-library/inp-inpw-inpd.md)|なし|
|[アウトプ、アウトpw、_outp、_outpw、_outpd](../c-runtime-library/outp-outpw-outpd.md)|なし|
|[_set_output_format](../c-runtime-library/set-output-format.md)|なし|

## <a name="removed-from-the-crt-in-earlier-versions-of-visual-studio"></a>Visual Studio の以前のバージョンで CRT から削除

[_lock](../c-runtime-library/lock.md)

[_unlock](../c-runtime-library/unlock.md)
