---
title: strerror_s、_strerror_s、_wcserror_s、__wcserror_s
ms.date: 11/04/2016
apiname:
- __wcserror_s
- _strerror_s
- _wcserror_s
- strerror_s
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
- wcserror_s
- __wcserror_s
- _tcserror_s
- _wcserror_s
- tcserror_s
- strerror_s
- _strerror_s
helpviewer_keywords:
- __wcserror_s function
- error messages, printing
- tcserror_s function
- printing error messages
- strerror_s function
- _wcserror_s function
- _tcserror_s function
- _strerror_s function
- wcserror_s function
- error messages, getting
ms.assetid: 9e5b15a0-efe1-4586-b7e3-e1d7c31a03d6
ms.openlocfilehash: 00ff9d0df1a78d07eaa509201fb998b30396cc4c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353823"
---
# <a name="strerrors-strerrors-wcserrors-wcserrors"></a>strerror_s、_strerror_s、_wcserror_s、__wcserror_s

システムのエラー メッセージ (**strerror_s**、 **_wcserror_s**) またはユーザー提供のエラー メッセージを印刷する (**_strerror_s**、 **_ _wcserror_s**). これらは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [strerror、_strerror、_wcserror、\__wcserror](strerror-strerror-wcserror-wcserror.md) です。

## <a name="syntax"></a>構文

```C
errno_t strerror_s(
   char *buffer,
   size_t numberOfElements,
   int errnum
);
errno_t _strerror_s(
   char *buffer,
   size_t numberOfElements,
   const char *strErrMsg
);
errno_t _wcserror_s(
   wchar_t *buffer,
   size_t numberOfElements,
   int errnum
);
errno_t __wcserror_s(
   wchar_t *buffer,
   size_t numberOfElements,
   const wchar_t *strErrMsg
);
template <size_t size>
errno_t strerror_s(
   char (&buffer)[size],
   int errnum
); // C++ only
template <size_t size>
errno_t _strerror_s(
   char (&buffer)[size],
   const char *strErrMsg
); // C++ only
template <size_t size>
errno_t _wcserror_s(
   wchar_t (&buffer)[size],
   int errnum
); // C++ only
template <size_t size>
errno_t __wcserror_s(
   wchar_t (&buffer)[size],
   const wchar_t *strErrMsg
); // C++ only
```

### <a name="parameters"></a>パラメーター

*バッファー*<br/>
エラー文字列を格納するバッファー。

*numberOfElements*<br/>
バッファーのサイズ。

*errnum*<br/>
エラー番号。

*strErrMsg*<br/>
ユーザーが指定したメッセージ。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。

### <a name="error-condtions"></a>エラー条件

|*バッファー*|*numberOfElements*|*strErrMsg*|内容*バッファー*|
|--------------|------------------------|-----------------|--------------------------|
|**NULL**|任意|任意|適用なし|
|任意|0|任意|変更されない|

## <a name="remarks"></a>Remarks

**Strerror_s**関数のマップ*errnum*エラー メッセージの文字列への文字列を返す*バッファー*します。 **_strerror_s**はエラー番号を受け取りませんの現在の値を使用して**errno**を適切なメッセージを確認します。 どちらも**strerror_s**も **_strerror_s**実際には、メッセージを出力します。そのため、出力関数を呼び出す必要があります[fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md):

```C
if (( _access( "datafile",2 )) == -1 )
{
   _strerror_s(buffer, 80);
   fprintf( stderr, buffer );
}
```

場合*strErrMsg*は**NULL**、 **_strerror_s**で文字列を返します*バッファー*ライブラリの最後の呼び出しのシステム エラー メッセージを含むエラーが発生しました。 エラー メッセージ文字列は、改行文字 (「\n」) で終了します。 場合*strErrMsg*が等しくない**NULL**、し **_strerror_s**で文字列を返します*バッファー* (順番に)、文字列メッセージを含む、コロン、空白、エラー、および改行文字、最後のライブラリ呼び出しのシステム エラー メッセージ。 文字列のメッセージの長さは、最大で 94 文字です。

これらの関数は、その長さを超えた場合に、エラー メッセージを切り捨てる*numberOfElements* -1。 結果の文字列*バッファー*が常に null で終了します。

実際のエラー番号 **_strerror_s**が変数に格納されている[errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)します。 システム エラー メッセージは、エラー番号順のメッセージの配列である変数 [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) を使用してアクセスできます。 **_strerror_s**を使用して、適切なエラー メッセージにアクセスする、 **errno**変数へのインデックスとして値 **_sys_errlist**します。 変数の値[_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)内の要素の最大数として定義される、 **_sys_errlist**配列。 正確な結果を生成するために呼び出す **_strerror_s**ライブラリ ルーチンがエラーを返した後すぐにします。 それ以外の場合、後続の呼び出しを**strerror_s**または **_strerror_s**を上書きできる、 **errno**値。

**_wcserror_s**と **_ _wcserror_s**のワイド文字バージョン**strerror_s**と **_strerror_s**、それぞれします。

これらの関数では、パラメーターの検証が行われます。 バッファーが場合**NULL**またはパラメーターのサイズが 0 の場合で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 関数を返すかどうかは、引き続き実行が許可された、 **EINVAL**設定と**errno**に**EINVAL**します。

**_strerror_s**、 **_wcserror_s**、および **_ _wcserror_s** ANSI 定義の一部ではないが、Microsoft の拡張機能では代わりにします。 使用しない移植性が必要な場合です。ANSI 互換性を使用して**strerror_s**代わりにします。

C++ では、テンプレートのオーバーロードによってこれらの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

これらの関数のデバッグ バージョンは、最初にバッファーを 0xFD で埋めます。 この動作を無効にするには、[_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md) を使用します。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror_s**|**strerror_s**|**strerror_s**|**_wcserror_s**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**strerror_s**, **_strerror_s**|\<string.h>|
|**_wcserror_s**, **__wcserror_s**|\<string.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[perror](perror-wperror.md)」の例をご覧ください。

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[perror、_wperror](perror-wperror.md)<br/>
