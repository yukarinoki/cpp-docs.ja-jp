---
title: strerror、_strerror、_wcserror、__wcserror
ms.date: 11/04/2016
apiname:
- strerror
- _strerror
- _wcserror
- __wcserror
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 4038fcc29c18e5d73024cbe5688c674e00d1409e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353860"
---
# <a name="strerror-strerror-wcserror-wcserror"></a>strerror、_strerror、_wcserror、__wcserror

システム エラー メッセージ文字列を取得します (**strerror**、 **_wcserror**) またはユーザー提供のエラー メッセージ文字列を書式設定 (**_strerror**、 **__wcserror**). これらの関数にはセキュリティが強化されたバージョンがあります。「[strerror_s、_strerror_s、_wcserror_s、\__wcserror_s](strerror-s-strerror-s-wcserror-s-wcserror-s.md)」をご覧ください。

## <a name="syntax"></a>構文

```C
char *strerror(
   int errnum
);
char *_strerror(
   const char *strErrMsg
);
wchar_t * _wcserror(
   int errnum
);
wchar_t * __wcserror(
   const wchar_t *strErrMsg
);
```

### <a name="parameters"></a>パラメーター

*errnum*<br/>
エラー番号。

*strErrMsg*<br/>
ユーザーが指定したメッセージ。

## <a name="return-value"></a>戻り値

これらの関数はすべて、エラー メッセージの文字列へのポインターを返します。 文字列は後続の呼び出しによって上書きされる可能性があります。

## <a name="remarks"></a>Remarks

**Strerror**関数のマップ*errnum*エラー メッセージ文字列を文字列にポインターを返します。 どちらも**strerror**も **_strerror**実際には、メッセージを出力します。そのため、出力関数を呼び出す必要がある[fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md):

```C
if (( _access( "datafile",2 )) == -1 )
   fprintf( stderr, _strerror(NULL) );
```

場合*strErrMsg*として渡される**NULL**、 **_strerror**エラーを生成した最後のライブラリ呼び出しのシステム エラー メッセージを含む文字列へのポインターを返します。 エラー メッセージ文字列は、改行文字 (「\n」) で終了します。 場合*strErrMsg*が等しくない**NULL**、し **_strerror** (順番に) 文字列のメッセージ、コロン、スペース、システム エラーを含む文字列へのポインターを返します最後のライブラリの呼び出し、および改行文字を生成するメッセージ。 文字列のメッセージの長さは、最大で 94 文字です。

実際のエラー番号 **_strerror**が変数に格納されている[errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)します。 正確な結果を生成するために呼び出す **_strerror**ライブラリ ルーチンがエラーを返した後すぐにします。 それ以外の場合、後続の呼び出しを**strerror**または **_strerror**を上書きできる、 **errno**値。

**_wcserror**と **_ _wcserror**のワイド文字バージョン**strerror**と **_strerror**、それぞれします。

**_strerror**、 **_wcserror**、および **_ _wcserror** ANSI 定義の一部ではない; は Microsoft 拡張機能とは使用しないことに移植可能なコードの先をお勧めします。 ANSI 互換性を使用して**strerror**代わりにします。

エラー文字列を取得する勧め**strerror**または **_wcserror**非推奨のマクロではなく[_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)と[_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)と非推奨の内部関数 **__sys_errlist**と **__sys_nerr**します。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror**|**strerror**|**strerror**|**_wcserror**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**strerror**|\<string.h>|
|**_strerror**|\<string.h>|
|**_wcserror**、 **_ _wcserror**|\<string.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[perror](perror-wperror.md)」の例をご覧ください。

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[perror、_wperror](perror-wperror.md)<br/>
