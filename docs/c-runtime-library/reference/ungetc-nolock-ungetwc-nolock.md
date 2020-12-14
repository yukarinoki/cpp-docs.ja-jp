---
description: '詳細については、次を参照してください: _ungetc_nolock、_ungetwc_nolock'
title: _ungetc_nolock、_ungetwc_nolock
ms.date: 4/2/2020
api_name:
- _ungetwc_nolock
- _ungetc_nolock
- _o__ungetc_nolock
- _o__ungetwc_nolock
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ungettc_nolock
- ungetwc_nolock
- ungetc_nolock
- _ungetc_nolock
- _ungetwc_nolock
helpviewer_keywords:
- _ungettc_nolock function
- _ungetwc_nolock function
- characters, pushing back onto stream
- _ungetc_nolock function
- ungetwc_nolock function
- ungettc_nolock function
- ungetc_nolock function
ms.assetid: aa02d5c2-1be1-46d2-a8c4-b61269e9d465
ms.openlocfilehash: 4b8e788cd64ca00de47109bb12780e2ccc7f4e0b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186624"
---
# <a name="_ungetc_nolock-_ungetwc_nolock"></a>_ungetc_nolock、_ungetwc_nolock

ストリームに文字をプッシュ バックします。

## <a name="syntax"></a>構文

```C
int _ungetc_nolock(
   int c,
   FILE *stream
);
wint_t _ungetwc_nolock(
   wint_t c,
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*c*<br/>
プッシュする文字。

*一連*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

成功した場合、これらの各関数は、文字引数 *c* を返します。 *C* をプッシュバックできない場合、または文字が読み取られなかった場合は、入力ストリームは変更されず、 **_ungetc_nolock** は **EOF** を返します。**_ungetwc_nolock** は **WEOF** を返します。 *Stream* が **NULL** の場合、 **EOF** または **WEOF** が返され、 **errno** が **EINVAL** に設定されます。

これらと他のエラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

これらの関数は、 **ungetc** および **ungetwc** のロックされていないバージョンです。 **_nolock** サフィックスが付いているバージョンは同じものですが、他のスレッドによる干渉から保護されない点が異なります。 他のスレッドをロックアウトするオーバーヘッドが発生しないため、処理が速くなる場合があります。 これらの関数は、シングルスレッド アプリケーション、呼び出し元のスコープで既にスレッド分離を処理している場合などのスレッドセーフなコンテキストでのみ使用してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ungettc_nolock**|**_ungetc_nolock**|**_ungetc_nolock**|**_ungetwc_nolock**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_ungetc_nolock**|\<stdio.h>|
|**_ungetwc_nolock**|\<stdio.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[getc、getwc](getc-getwc.md)<br/>
[putc、putwc](putc-putwc.md)<br/>
