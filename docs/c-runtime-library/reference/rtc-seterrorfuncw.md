---
title: _RTC_SetErrorFuncW | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _RTC_SetErrorFuncW
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
apitype: DLLExport
f1_keywords:
- _RTC_SetErrorFuncW
- RTC_SetErrorFuncW
dev_langs:
- C++
helpviewer_keywords:
- run-time errors
- RTC_SetErrorFuncW function
- _RTC_error_fnW typedef
- _RTC_SetErrorFuncW function
- RTC_error_fnW typedef
ms.assetid: b3e0d71f-1bd3-4c37-9ede-2f638eb3c81a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cf610316c504e61d56556a20797f55d2906bca27
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="rtcseterrorfuncw"></a>_RTC_SetErrorFuncW

実行時エラー チェック (RTC) を報告するためのハンドラーとして関数を指定します。

## <a name="syntax"></a>構文

```C
_RTC_error_fnW _RTC_SetErrorFuncW(
   _RTC_error_fnW function
);
```

### <a name="parameters"></a>パラメーター

*関数*<br/>
実行時エラー チェックを処理する関数のアドレス。

## <a name="return-value"></a>戻り値

以前に定義されたエラー関数です。または**NULL**以前に定義された関数が存在しない場合。

## <a name="remarks"></a>コメント

新しいコードでのみ使用して **_RTC_SetErrorFuncW**です。 **_RTC_SetErrorFunc**は旧バージョンとの互換性のため、ライブラリにのみ含まれます。

**_RTC_SetErrorFuncW**コールバックは、リンクされたコンポーネントにのみ適用されますが、グローバルにありません。

確認して、アドレスに渡す **_RTC_SetErrorFuncW**は有効なエラー処理関数の名前にします。

かどうか、エラーが割り当てられて-1 の型を使用して[_RTC_SetErrorType](rtc-seterrortype.md)、エラー処理関数は呼び出されません。

この関数を呼び出すには、まず、実行時エラー チェックの初期化関数の 1 つを呼び出す必要があります。 詳細については、「 [Using Run-Time Checks Without the C Run-Time Library](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library)」を参照してください。

**_RTC_error_fnW** は次のように定義されています。

> **int の typedef (_ _cdecl \*_RTC_error_fnW) (int** *errorType* **、const wchar_t \***  *filename* **、int***linenumber* **、const wchar_t \***  *moduleName* **、const wchar_t \*** *形式* **,...)。** 

それぞれの文字について以下に説明します。

*errorType*で指定されているエラーの種類[_RTC_SetErrorType](rtc-seterrortype.md)です。

*filename*障害が発生したソース ファイルまたはデバッグ情報がない場合は null です。

*linenumber*行では、 *filename*障害が発生したか、デバッグ情報がない場合は 0 です。

*moduleName* DLL または実行可能ファイル名が、エラーが発生します。

*形式*残りのパラメーターを使用して、エラー メッセージを表示する文字列。 VA_ARGLIST の最初の引数は、発生した RTC エラーの番号です。

**_RTC_error_fnW** の使用例については、「[ネイティブ ランタイム チェックのカスタマイズ](/visualstudio/debugger/native-run-time-checks-customization)」をご覧ください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_RTC_SetErrorFuncW**|\<rtcapi.h>|

詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="see-also"></a>関連項目

[_CrtDbgReport、_CrtDbgReportW](crtdbgreport-crtdbgreportw.md)<br/>
[ランタイム エラー チェック](../../c-runtime-library/run-time-error-checking.md)<br/>
