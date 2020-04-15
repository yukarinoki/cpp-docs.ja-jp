---
title: strerror、_strerror、_wcserror、__wcserror
description: Microsoft C ランタイム ライブラリ (CRT) 関数 strerror、_strerror、_wcserror、および__wcserrorについて説明します。
ms.date: 4/2/2020
api_name:
- strerror
- _strerror
- _wcserror
- __wcserror
- _o___wcserror
- _o__strerror
- _o__wcserror
- _o_strerror
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __sys_errlist
- wcserror
- _strerror
- __wcserror
- strerror
- __sys_nerr
- _tcserror
- _wcserror
- tcserror
helpviewer_keywords:
- strerror function
- _strerror function
- __sys_errlist
- wcserror function
- error messages, printing
- __sys_nerr
- tcserror function
- printing error messages
- _wcserror function
- _tcserror function
- __wcserror function
- error messages, getting
ms.assetid: 27b72255-f627-43c0-8836-bcda8b003e14
ms.openlocfilehash: 9eecb7376cf476f0128dc20c8884746a3b4d47d9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337329"
---
# <a name="strerror-_strerror-_wcserror-__wcserror"></a>strerror、_strerror、_wcserror、__wcserror

システム エラー メッセージ文字列 (**strerror**、 **_wcserror**) を取得するか、ユーザー指定のエラー メッセージ文字列 (**_strerror**、 **__wcserror**) を書式設定します。 これらの関数にはセキュリティが強化されたバージョンがあります。「[strerror_s、_strerror_s、_wcserror_s、\__wcserror_s](strerror-s-strerror-s-wcserror-s-wcserror-s.md)」をご覧ください。

## <a name="syntax"></a>構文

```C
char * strerror(
   int errnum );

char * _strerror(
   const char *strErrMsg );

wchar_t * _wcserror(
   int errnum );

wchar_t * __wcserror(
   const wchar_t *strErrMsg );
```

### <a name="parameters"></a>パラメーター

*エラーナム*\
エラー番号。

*メッセージ*\
ユーザーが指定したメッセージ。

## <a name="return-value"></a>戻り値

これらの関数はすべて、ランタイムが所有するスレッド ローカル ストレージ バッファー内のエラー メッセージ文字列へのポインターを返します。 後で同じスレッドを呼び出す場合、この文字列を上書きできます。

## <a name="remarks"></a>解説

**strerror**関数はエラー メッセージ文字列に*errnum*をマップし、文字列へのポインターを返します。 **strerror**関数と **_strerror**関数は、実際にはメッセージを出力しません。 印刷するには[、fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md)などの出力関数を呼び出します。

```C
if (( _access( "datafile", 2 )) == -1 )
   fprintf( stderr, _strerror(NULL) );
```

*strErrMsg*が**NULL**として渡された場合 **、_strerrorは**文字列へのポインターを返します。 エラーを生成した最後のライブラリー呼び出しに対するシステム・エラー・メッセージが含まれています。 エラー メッセージ文字列は、改行文字 (「\n」) で終了します。 *strErrMsg*が**NULL**でない場合、文字列には*strErrMsg*文字列、コロン、スペース、システム エラー メッセージ、および改行文字が順番に含まれます。 文字列メッセージは、長さ 94 文字までで、幅の狭い (**_strerror**) またはワイド (**__wcserror**) の文字で指定できます。

**_strerror**の実際のエラー番号は変数[errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)に格納されます。 正確な結果を生成するには、ライブラリ ルーチンがエラーを返した直後に **_strerror**呼び出します。 それ以外の場合は、ライブラリ ルーチンを後で呼び出した場合 **、errno**値が上書きされる可能性があります。

**_wcserror**と **__wcserror**は、 **strerror**および **_strerror**のワイド文字バージョンです。

**_strerror**、 **_wcserror**、および **__wcserror**は、標準 C ライブラリの一部ではなく、マイクロソフト固有のものです。 移植可能なコードを使用する場所で使用することはお勧めしません。 標準 C 互換性の場合は、代わりに**strerror を**使用します。

エラー文字列を取得するには、_sys_errlistおよび[_sys_nerr、](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)および廃止された内部関数の[代](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)わりに**strerror**または **_wcserror__sys_errlist**および **__sys_nerr**することをお勧めします。 **__sys_errlist**

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト・ルーチン・マッピング

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror**|**strerror**|**strerror**|**_wcserror**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**strerror**|\<string.h>|
|**_strerror**|\<string.h>|
|**_wcserror**, **__wcserror**|\<string.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[perror](perror-wperror.md)」の例をご覧ください。

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)\
[クリアラー](clearerr.md)\
[エラー](ferror.md)\
[perror、_wperror](perror-wperror.md)
