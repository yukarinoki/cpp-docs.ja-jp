---
title: strerror、_strerror、_wcserror、__wcserror
ms.date: 11/04/2016
api_name:
- strerror
- _strerror
- _wcserror
- __wcserror
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
ms.openlocfilehash: 0b4d70687bc2f428162d035c80d6bc8525a8fb9e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70958146"
---
# <a name="strerror-_strerror-_wcserror-__wcserror"></a>strerror、_strerror、_wcserror、__wcserror

システムエラーメッセージ文字列 (**strerror**、 **_wcserror**) を取得するか、ユーザーが指定したエラーメッセージ文字列 ( **_strerror**、 **__wcserror**) を書式設定します。 これらの関数にはセキュリティが強化されたバージョンがあります。「[strerror_s、_strerror_s、_wcserror_s、\__wcserror_s](strerror-s-strerror-s-wcserror-s-wcserror-s.md)」をご覧ください。

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

**Strerror**関数は、 *errnum*をエラーメッセージ文字列にマップし、文字列へのポインターを返します。 **Strerror**も **_strerror**も、実際にはメッセージを出力しません。そのためには、 [fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md)などの出力関数を呼び出す必要があります。

```C
if (( _access( "datafile",2 )) == -1 )
   fprintf( stderr, _strerror(NULL) );
```

*StrErrMsg*が**NULL**として渡された場合、 **_strerror**は、エラーを生成した最後のライブラリの呼び出しのシステムエラーメッセージを含む文字列へのポインターを返します。 エラー メッセージ文字列は、改行文字 (「\n」) で終了します。 *StrErrMsg*が**NULL**でない場合、 **_strerror**は、文字列メッセージ、コロン、空白、エラーを生成した最後のライブラリの呼び出しのシステムエラーメッセージ、および改行を含む文字列へのポインターを返します。記号. 文字列のメッセージの長さは、最大で 94 文字です。

**_Strerror**の実際のエラー番号は、変数[errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)に格納されます。 正確な結果を生成するには、ライブラリルーチンからエラーが返された直後に **_strerror**を呼び出します。 それ以外の場合、 **strerror**または **_strerror**を呼び出すと、 **errno**値が上書きされる可能性があります。

**_wcserror**と **__wcserror**は、それぞれ**strerror**と **_strerror**のワイド文字バージョンです。

**_strerror**、 **_wcserror**、および **__wcserror**は、ANSI 定義の一部ではありません。これらは Microsoft 拡張機能であり、移植性のあるコードを作成する場合は使用しないことをお勧めします。 ANSI 互換の場合は、代わりに**strerror**を使用してください。

エラー文字列を取得するには、非推奨のマクロ[_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)と[_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 、および非推奨の内部関数 **__sys_errlist**と **__sys_nerr**の代わりに、 **strerror**または **_wcserror**を使用することをお勧めします。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror**|**strerror**|**strerror**|**_wcserror**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**strerror**|\<string.h>|
|**_strerror**|\<string.h>|
|**_wcserror**、 **__wcserror**|\<string.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[perror](perror-wperror.md)」の例をご覧ください。

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[perror、_wperror](perror-wperror.md)<br/>
