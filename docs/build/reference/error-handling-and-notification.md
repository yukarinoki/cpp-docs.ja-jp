---
title: エラー処理と通知
description: 詳細については、「DLL 遅延読み込みエラー処理と通知」を参照してください。
ms.date: 01/19/2021
helpviewer_keywords:
- error handling, and notification
ms.openlocfilehash: efff7ba9956bee8fe6ccf1df96a3f4b49852ce43
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522561"
---
# <a name="error-handling-and-notification"></a>エラー処理と通知

プログラムが遅延読み込みされた Dll を使用している場合、プログラムの実行中に発生したエラーによってハンドルされない例外が発生するため、エラーを確実に処理する必要があります。 エラー処理は、フックを使用した復旧と、例外によるレポートの2つの部分で構成されます。

DLL 遅延読み込みエラー処理と通知の詳細については、「 [ヘルパー関数に](understanding-the-helper-function.md)ついて」を参照してください。

フック関数の詳細については、「 [構造体と定数の定義](understanding-the-helper-function.md#structure-and-constant-definitions)」を参照してください。

## <a name="recovery-through-a-hook"></a>フックによる復旧

コードで障害が発生したときに回復するか、別のライブラリまたはルーチンを提供することが必要になる場合があります。 代替コードを提供できるヘルパー関数にフックを提供したり、状況を修正したりすることができます。 フックルーチンは、処理を続行できるように適切な値を返す必要があり `HINSTANCE` ます (または `FARPROC` )。 または、0を返して、例外をスローする必要があることを示します。 また、独自の例外 `longjmp` をスローしたり、フックから除外したりすることもできます。 通知フックとエラーフックがあります。 同じルーチンを両方に使用できます。

## <a name="notification-hooks"></a><a name="notification-hooks"></a> 通知フック

遅延読み込み通知フックは、ヘルパールーチンで次のアクションが実行される直前に呼び出されます。

- ライブラリへの格納されているハンドルが、既に読み込まれているかどうかがチェックされます。

- `LoadLibrary` は、DLL の読み込みを試行するために呼び出されます。

- `GetProcAddress` は、プロシージャのアドレスを取得しようとするために呼び出されます。

- 遅延インポート読み込みサンクに戻ります。

通知フックが有効になっています。

- `__pfnDliNotifyHook2`通知を受け取る独自の関数を指すように初期化されたポインターの新しい定義を指定します。

   \- または -

- `__pfnDliNotifyHook2`プログラムが遅延読み込みを行う DLL の呼び出しの前に、フック関数へのポインターを設定します。

通知がの場合 `dliStartProcessing` 、フック関数は次を返すことができます。

- `NULL`

   既定のヘルパーは、DLL の読み込みを処理します。 情報提供を目的としてのみを呼び出すと便利です。

- 関数ポインター

   既定の遅延読み込み処理をバイパスします。 独自の読み込みハンドラーを指定できます。

通知がの場合 `dliNotePreLoadLibrary` 、フック関数は次を返すことができます。

- 情報通知のみを必要とする場合は0。

- `HMODULE`Dll 自体が読み込まれた場合は、読み込まれた dll の。

通知がの場合 `dliNotePreGetProcAddress` 、フック関数は次を返すことができます。

- 情報通知のみを必要とする場合は0。

- フック関数がアドレス自体を取得する場合は、インポートされた関数のアドレス。

通知がの場合 `dliNoteEndProcessing` 、フック関数の戻り値は無視されます。

このポインターが初期化されている場合 (0 以外)、遅延読み込みヘルパーは、実行中の特定の通知ポイントで関数を呼び出します。 関数ポインターには次の定義があります。

```C
// The "notify hook" gets called for every call to the
// delay load helper.  This allows a user to hook every call and
// skip the delay load helper entirely.
//
// dliNotify == {
//  dliStartProcessing |
//  dliNotePreLoadLibrary  |
//  dliNotePreGetProc |
//  dliNoteEndProcessing}
//  on this call.
//
ExternC
PfnDliHook   __pfnDliNotifyHook2;

// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}
ExternC
PfnDliHook   __pfnDliFailureHook2;
```

通知は、 `DelayLoadInfo` 通知値と共にフック関数に構造体を渡します。 このデータは、遅延読み込みヘルパールーチンによって使用されるデータと同じです。 通知値は、 [構造体と定数の定義](understanding-the-helper-function.md#structure-and-constant-definitions)で定義されている値のいずれかになります。

## <a name="failure-hooks"></a><a name="failure-hooks"></a> エラーフック

エラーフックは、 [通知フック](#notification-hooks)と同じ方法で有効になります。 フックルーチンは、処理を続行できるように適切な値を返す必要があり `HINSTANCE` ます (または)。0の場合は、例外がスローされることを `FARPROC` 示します。

ユーザー定義関数を参照するポインター変数は次のとおりです。

```C
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}
ExternC
PfnDliHook   __pfnDliFailureHook2;
```

構造体には、 **`DelayLoadInfo`** エラーの詳細なレポートに必要なすべての関連データ (からの値を含む) が含まれ `GetLastError` ます。

通知がの場合 **`dliFailLoadLib`** 、フック関数は次を返すことができます。

- エラーを処理できない場合は0。

- `HMODULE`エラーフックによって問題が修正され、ライブラリ自体が読み込まれた場合は。

通知がの場合 **`dliFailGetProc`** 、フック関数は次を返すことができます。

- エラーを処理できない場合は0。

- エラーフックがアドレス自体を取得するのに成功した場合は、有効な proc address (import 関数のアドレス)。

## <a name="report-by-using-an-exception"></a>例外を使用したレポート

エラーを処理するために必要なものがすべてプロシージャを中止するだけの場合は、ユーザーコードが例外を処理できる限り、フックは必要ありません。

## <a name="delay-load-exception-codes"></a><a name="delay-load-exception-codes"></a> 遅延読み込みの例外コード

構造化例外コードは、遅延読み込み中にエラーが発生した場合に発生する可能性があります。 例外値は、マクロを使用して指定し `VcppException` ます。

```C
//
// Exception information
//
#define FACILITY_VISUALCPP  ((LONG)0x6d)
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)
```

エラーの場合 `LoadLibrary` 、標準 `VcppException(ERROR_SEVERITY_ERROR, ERROR_MOD_NOT_FOUND)` がスローされます。 エラーの場合 `GetProcAddress` 、スローされたエラーは `VcppException(ERROR_SEVERITY_ERROR, ERROR_PROC_NOT_FOUND)` です。 この例外は、構造体へのポインターを渡し `DelayLoadInfo` ます。 この値は、 `LPDWORD` によってから取得された、 `GetExceptionInformation` [`EXCEPTION_RECORD`](/windows/win32/api/winnt/ns-winnt-exception_record) 構造体の `ExceptionInformation[0]` フィールドにあります。

フィールドに正しくないビットが設定されている場合は、 `grAttrs` 例外 `ERROR_INVALID_PARAMETER` がスローされます。 この例外は、すべてのインテントと目的で致命的です。

詳細については、「 [構造体と定数の定義](understanding-the-helper-function.md#structure-and-constant-definitions)」を参照してください。

## <a name="see-also"></a>関連項目

[リンカーによる DLL の遅延読み込み](linker-support-for-delay-loaded-dlls.md)
