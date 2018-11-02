---
title: _invalid_parameter、_invalid_parameter_noinfo、_invalid_parameter_noinfo_noreturn、_invoke_watson
ms.date: 11/04/2016
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
ms.openlocfilehash: e43d5caaeebb6303d209d870c804357117812985
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50478365"
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

*式*<br/>
有効でないソース コード パラメーターの式を表す文字列。

*function_name*<br/>
ハンドラーを呼び出した関数の名前。

*file_name*<br/>
ハンドラーが呼び出されたソース コード ファイル。

*line_number*<br/>
ハンドラーが呼び出されたソース コードの行番号。

*reserved*<br/>
使用されません。

## <a name="return-value"></a>戻り値

これらの関数は値を返しません。 **_Invalid_parameter_noinfo_noreturn**と **_invoke_watson** 、呼び出し元に、場合によっては、関数を返さない **_invalid_parameter**と **_invalid_parameter_noinfo**呼び出し元に戻らない場合があります。

## <a name="remarks"></a>Remarks

有効でないパラメーターが C ランタイム ライブラリ関数に渡された場合、ライブラリ関数は、*無効なパラメーター ハンドラー*を呼び出します。これは、いくつかの作業のうちのいずれかを行うためにプログラマによって指定された関数です。 たとえば、問題をユーザーにレポートする、ログに書き込む、デバッガーで中断する、プログラムを終了する、または何も行わない、などです。 関数が既定のハンドラーで、プログラマが指定されていない場合 **_invoke_watson**が呼び出されます。

既定では、有効でないパラメーターが、デバッグ コードで識別される CRT ライブラリ関数を呼び出す関数 **_invalid_parameter** verbose パラメーターを使用します。 非デバッグ コードで、 **_invalid_parameter_noinfo**関数を呼び出す、呼び出し、 **_invalid_parameter**空のパラメーターを使用して機能します。 非デバッグ CRT ライブラリ関数がプログラムの終了が必要な場合、 **_invalid_parameter_noinfo_noreturn**関数を呼び出す、呼び出し、 **_invalid_parameter**空を使用して機能呼び出して、パラメーターの後に、 **_invoke_watson**プログラムの終了を強制する関数。

**_Invalid_parameter**関数チェックとユーザー定義の無効なパラメーター ハンドラーが設定されているかどうか、そうである場合は関数を呼び出します。 たとえば、現在のスレッドで [set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) の呼び出しでユーザー定義のスレッド ローカル ハンドラーが設定されている場合、それを呼び出し、次いでその関数は戻ります。 それ以外の場合、[set_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) の呼び出しでユーザー定義の無効なグローバル パラメーター ハンドラーが設定されているなら、それを呼び出し、次いでその関数は戻ります。 それ以外の場合、既定のハンドラー **_invoke_watson**が呼び出されます。 既定の動作 **_invoke_watson**をプログラムを終了します。 ユーザー定義のハンドラーは終了するか、戻るかのいずれかです。 確実に回復できるのでない限り、ユーザー定義のハンドラーでプログラムを終了することをお勧めします。

ときに、既定のハンドラー **_invoke_watson**と呼ばれる場合は、プロセッサがサポートしている場合、 [_ _fastfail を](../../intrinsics/fastfail.md)操作のパラメーターを使用してメソッドが呼び出された**FAST_FAIL_INVALID_ARG**プロセスが終了します。 それ以外の場合、Fail Fast 例外が発生します。これは、アタッチされているデバッガーでキャッチできます。 プロセスの継続が許可された場合は、Windows への呼び出しによって終了**TerminateProcess**の例外コード状態を使用して機能**STATUS_INVALID_CRUNTIME_PARAMETER**します。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|------------------|
|**_invalid_parameter**、 **_invalid_parameter_noinfo**、 **_invalid_parameter_noinfo_noreturn**、 **_invoke_watson**|\<corecrt.h >|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[_get_invalid_parameter_handler、_get_thread_local_invalid_parameter_handler](get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)<br/>
[_set_invalid_parameter_handler、_set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)<br/>
[パラメーターの検証](../../c-runtime-library/parameter-validation.md)<br/>
