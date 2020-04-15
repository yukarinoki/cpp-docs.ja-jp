---
title: _invalid_parameter、_invalid_parameter_noinfo、_invalid_parameter_noinfo_noreturn、_invoke_watson
ms.date: 4/2/2020
api_name:
- _invalid_parameter
- _invalid_parameter_noinfo
- _invalid_parameter_noinfo_noreturn
- _invoke_watson
- _o__invalid_parameter_noinfo
- _o__invalid_parameter_noinfo_noreturn
api_location:
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 0f0a3ea3e1f2e43d53650b4017905c696269ce20
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343940"
---
# <a name="_invalid_parameter-_invalid_parameter_noinfo-_invalid_parameter_noinfo_noreturn-_invoke_watson"></a>_invalid_parameter、_invalid_parameter_noinfo、_invalid_parameter_noinfo_noreturn、_invoke_watson

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

*予約*<br/>
未使用。

## <a name="return-value"></a>戻り値

これらの関数は値を返しません。 **_invalid_parameter_noinfo_noreturn**関数と **_invoke_watson**関数は呼び出し元に戻らないので、場合によっては **、_invalid_parameter**と **_invalid_parameter_noinfo**が呼び出し元に戻らない場合があります。

## <a name="remarks"></a>解説

有効でないパラメーターが C ランタイム ライブラリ関数に渡された場合、ライブラリ関数は、*無効なパラメーター ハンドラー*を呼び出します。これは、いくつかの作業のうちのいずれかを行うためにプログラマによって指定された関数です。 たとえば、問題をユーザーにレポートする、ログに書き込む、デバッガーで中断する、プログラムを終了する、または何も行わない、などです。 プログラマが関数を指定しない場合は、既定のハンドラ **_invoke_watson**が呼び出されます。

既定では、デバッグ コードで無効なパラメーターが識別されると、CRT ライブラリ関数は詳細パラメーター**を使用して関数_invalid_parameter**呼び出します。 非デバッグ コードでは **、_invalid_parameter_noinfo**関数が呼び出され、空のパラメーターを使用して **_invalid_parameter**関数が呼び出されます。 非デバッグ CRT ライブラリ関数がプログラムの終了を必要とする場合は **、_invalid_parameter_noinfo_noreturn**関数が呼び出され、空のパラメーターを使用して **_invalid_parameter**関数を呼び出し、その後**に _invoke_watson**関数を呼び出してプログラムの終了を強制します。

**_invalid_parameter**関数は、ユーザー定義の無効なパラメーター ハンドラーが設定されているかどうかを確認し、設定されている場合はそれを呼び出します。 たとえば、現在のスレッドで [set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) の呼び出しでユーザー定義のスレッド ローカル ハンドラーが設定されている場合、それを呼び出し、次いでその関数は戻ります。 それ以外の場合、[set_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) の呼び出しでユーザー定義の無効なグローバル パラメーター ハンドラーが設定されているなら、それを呼び出し、次いでその関数は戻ります。 それ以外の場合は、既定のハンドラー **_invoke_watson**が呼び出されます。 **_invoke_watson**の既定の動作は、プログラムを終了することです。 ユーザー定義のハンドラーは終了するか、戻るかのいずれかです。 確実に回復できるのでない限り、ユーザー定義のハンドラーでプログラムを終了することをお勧めします。

既定のハンドラー **_invoke_watson**が呼び出されると、プロセッサが[__fastfail](../../intrinsics/fastfail.md)操作をサポートしている場合、FAST_FAIL_INVALID_ARG**のパラメーター**を使用して呼び出され、プロセスが終了します。 それ以外の場合、Fail Fast 例外が発生します。これは、アタッチされているデバッガーでキャッチできます。 プロセスの続行が許可されている場合は、例外コードの状態を使用して Windows **TerminateProcess**関数を呼び出すことによって終了**STATUS_INVALID_CRUNTIME_PARAMETER。**

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|
|--------------|------------------|
|**_invalid_parameter**, **_invalid_parameter_noinfo**, **_invalid_parameter_noinfo_noreturn**, **_invoke_watson**|\<corecrt.h >|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[_get_invalid_parameter_handler、_get_thread_local_invalid_parameter_handler](get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)<br/>
[_set_invalid_parameter_handler、_set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)<br/>
[パラメーターの検証](../../c-runtime-library/parameter-validation.md)<br/>
