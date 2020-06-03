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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 7138e9cb7381e4d40911054e1473536b6e639e2d
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919822"
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

*式 (expression)*<br/>
有効でないソース コード パラメーターの式を表す文字列。

*function_name*<br/>
ハンドラーを呼び出した関数の名前。

*file_name*<br/>
ハンドラーが呼び出されたソース コード ファイル。

*line_number*<br/>
ハンドラーが呼び出されたソース コードの行番号。

*確保*<br/>
未使用。

## <a name="return-value"></a>戻り値

これらの関数は値を返しません。 **_Invalid_parameter_noinfo_noreturn**関数と **_invoke_watson**関数は呼び出し元に戻りません。場合によっては、 **_invalid_parameter**と **_invalid_parameter_noinfo**が呼び出し元に戻らないことがあります。

## <a name="remarks"></a>解説

有効でないパラメーターが C ランタイム ライブラリ関数に渡された場合、ライブラリ関数は、*無効なパラメーター ハンドラー*を呼び出します。これは、いくつかの作業のうちのいずれかを行うためにプログラマによって指定された関数です。 たとえば、問題をユーザーにレポートする、ログに書き込む、デバッガーで中断する、プログラムを終了する、または何も行わない、などです。 プログラマによって関数が指定されていない場合、既定のハンドラーである **_invoke_watson**が呼び出されます。

既定では、有効でないパラメーターがデバッグコードで識別されると、CRT ライブラリ関数は、verbose パラメーターを使用して **_invalid_parameter**関数を呼び出します。 非デバッグコードでは、 **_invalid_parameter_noinfo**関数が呼び出されます。この関数は、空のパラメーターを使用して **_invalid_parameter**関数を呼び出します。 非デバッグ CRT ライブラリ関数でプログラムの終了が必要な場合は、 **_invalid_parameter_noinfo_noreturn**関数が呼び出されます。この関数は、空のパラメーターを使用して **_invalid_parameter**関数を呼び出した後、 **_invoke_watson**関数を呼び出してプログラムを強制的に終了します。

**_Invalid_parameter**関数は、ユーザー定義の無効なパラメーターハンドラーが設定されているかどうかを確認し、存在する場合はそれを呼び出します。 たとえば、現在のスレッドで [set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) の呼び出しでユーザー定義のスレッド ローカル ハンドラーが設定されている場合、それを呼び出し、次いでその関数は戻ります。 それ以外の場合、[set_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) の呼び出しでユーザー定義の無効なグローバル パラメーター ハンドラーが設定されているなら、それを呼び出し、次いでその関数は戻ります。 それ以外の場合、既定のハンドラー **_invoke_watson**が呼び出されます。 **_Invoke_watson**の既定の動作では、プログラムが終了します。 ユーザー定義のハンドラーは終了するか、戻るかのいずれかです。 確実に回復できるのでない限り、ユーザー定義のハンドラーでプログラムを終了することをお勧めします。

既定のハンドラー **_invoke_watson**が呼び出されると、プロセッサが[__fastfail](../../intrinsics/fastfail.md)操作をサポートしている場合は、 **FAST_FAIL_INVALID_ARG**のパラメーターを使用して呼び出され、プロセスが終了します。 それ以外の場合、Fail Fast 例外が発生します。これは、アタッチされているデバッガーでキャッチできます。 プロセスの継続が許可された場合、 **STATUS_INVALID_CRUNTIME_PARAMETER**の例外コードの状態を使用して、Windows **TerminateProcess**関数への呼び出しによって終了されます。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|------------------|
|**_invalid_parameter**、 **_invalid_parameter_noinfo**、 **_invalid_parameter_noinfo_noreturn**、 **_invoke_watson**|\<corecrt.h >|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[_get_invalid_parameter_handler、_get_thread_local_invalid_parameter_handler](get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)<br/>
[_set_invalid_parameter_handler、_set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)<br/>
[パラメーターの検証](../../c-runtime-library/parameter-validation.md)<br/>
