---
title: _invalid_parameter、_invalid_parameter_noinfo、_invalid_parameter_noinfo_noreturn、_invoke_watson | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
apiname:
- _invalid_parameter
- _invalid_parameter_noinfo
- _invalid_parameter_noinfo_noreturn
- _invoke_watson
apilocation:
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- CORECRT/_invalid_parameter
- _invalid_parameter
- CORECRT/_invalid_parameter_noinfo
- _invalid_parameter_noinfo
- CORECRT/_invalid_parameter_noinfo_noreturn
- _invalid_parameter_noinfo_noreturn
- CORECRT/_invoke_watson
- _invoke_watson
ms.assetid: a4d6f1fd-ce56-4783-8719-927151a7a814
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6b0fecd7eefe9ac6a7a479fb12475b2b1c769cf4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="invalidparameter-invalidparameternoinfo-invalidparameternoinfonoreturn-invokewatson"></a>_invalid_parameter、_invalid_parameter_noinfo、_invalid_parameter_noinfo_noreturn、_invoke_watson

これらの関数は、CRT ライブラリ関数に渡された有効でないパラメーターを処理するために C ランタイム ライブラリによって使用されます。 有効でないパラメーターの既定の処理またはカスタマイズ可能な処理をサポートするために、自分のコードでこれらの関数を使用することもできます。

## <a name="syntax"></a>構文

```C
extern "C" void __cdecl
_invalid_parameter(
    wchar_t const* const expression,
    wchar_t const* const function_name,
    wchar_t const* const file_name,
    unsigned int   const line_number,
    uintptr_t      const reserved);

extern "C" void __cdecl
_invalid_parameter_noinfo(void);

extern "C" __declspec(noreturn) void __cdecl
_invalid_parameter_noinfo_noreturn(void);

extern "C" __declspec(noreturn) void __cdecl
_invoke_watson(
    wchar_t const* const expression,
    wchar_t const* const function_name,
    wchar_t const* const file_name,
    unsigned int   const line_number,
    uintptr_t      const reserved);
```

## <a name="parameters"></a>パラメーター

*式*が無効なソース コード パラメーターの式を表す文字列。

*function_name*ハンドラーが呼び出される関数の名前。

*file_name*ハンドラーが呼び出されたソース コード ファイル。

*line_number*ハンドラーが呼び出されたソース コード内の行番号。

*予約済み*未使用。

## <a name="return-value"></a>戻り値

これらの関数は値を返しません。 **_Invalid_parameter_noinfo_noreturn**と **_invoke_watson** 、呼び出し元に、場合によっては、関数から返されません **_invalid_parameter**と **_invalid_parameter_noinfo**呼び出し元を返さない可能性があります。

## <a name="remarks"></a>コメント

有効でないパラメーターが C ランタイム ライブラリ関数に渡された場合、ライブラリ関数は、*無効なパラメーター ハンドラー*を呼び出します。これは、いくつかの作業のうちのいずれかを行うためにプログラマによって指定された関数です。 たとえば、問題をユーザーにレポートする、ログに書き込む、デバッガーで中断する、プログラムを終了する、または何も行わない、などです。 プログラマが、既定のハンドラーで関数が指定されていない場合 **_invoke_watson**と呼びます。

既定では、デバッグのコードで有効でないパラメーターが特定される CRT ライブラリ関数、関数を呼び出す **_invalid_parameter** verbose パラメーターを使用します。 非デバッグのコードで、 **_invalid_parameter_noinfo**関数が呼び出されると、どの呼び出し、 **_invalid_parameter**の空のパラメーターを使用して機能します。 非デバッグ CRT ライブラリ関数には、プログラムの終了が必要な場合、 **_invalid_parameter_noinfo_noreturn**関数が呼び出されると、どの呼び出し、 **_invalid_parameter**空を使用して機能呼び出しによって、パラメーターの後に、 **_invoke_watson**プログラムの終了を強制する関数。

**_Invalid_parameter**関数チェックは、ユーザー定義の無効なパラメーター ハンドラーが設定されているかどうかと、その呼び出し元。 たとえば、現在のスレッドで [set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) の呼び出しでユーザー定義のスレッド ローカル ハンドラーが設定されている場合、それを呼び出し、次いでその関数は戻ります。 それ以外の場合、[set_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) の呼び出しでユーザー定義の無効なグローバル パラメーター ハンドラーが設定されているなら、それを呼び出し、次いでその関数は戻ります。 それ以外の場合、既定のハンドラー **_invoke_watson**と呼びます。 既定の動作 **_invoke_watson**が、プログラムを終了します。 ユーザー定義のハンドラーは終了するか、戻るかのいずれかです。 確実に回復できるのでない限り、ユーザー定義のハンドラーでプログラムを終了することをお勧めします。

ときに既定のハンドラー **_invoke_watson**が呼び出されると、プロセッサがサポートされている場合、 [__fastfail](../../intrinsics/fastfail.md)操作のパラメーターを使用してメソッドが呼び出された**FAST_FAIL_INVALID_ARG**およびプロセスが終了します。 それ以外の場合、Fail Fast 例外が発生します。これは、アタッチされているデバッガーでキャッチできます。 プロセスの継続が許可された場合は、Windows への呼び出しによって終了**TerminateProcess**の例外コードの状態を使用して機能**STATUS_INVALID_CRUNTIME_PARAMETER**です。

## <a name="requirements"></a>要件

|関数|必須ヘッダー|
|--------------|------------------|
|**_invalid_parameter**、 **_invalid_parameter_noinfo**、 **_invalid_parameter_noinfo_noreturn**、 **_invoke_watson**|\<corecrt.h >|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[_get_invalid_parameter_handler、_get_thread_local_invalid_parameter_handler](get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)<br/>
[_set_invalid_parameter_handler、_set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)<br/>
[パラメーターの検証](../../c-runtime-library/parameter-validation.md)<br/>
