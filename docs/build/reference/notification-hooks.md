---
description: 詳細については、「遅延読み込み通知フック」を参照してください。
title: 通知フック
ms.date: 01/19/2021
helpviewer_keywords:
- delayed loading of DLLs, notification hooks
ms.openlocfilehash: 401ae9099afcf00dc280bb4f9e5f7016a4cbc640
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667544"
---
# <a name="notification-hooks"></a>通知フック

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

通知は、 `DelayLoadInfo` 通知値と共にフック関数に構造体を渡します。 このデータは、遅延読み込みヘルパールーチンによって使用されるデータと同じです。 通知値は、 [構造体と定数の定義](structure-and-constant-definitions.md)で定義されている値のいずれかになります。

## <a name="see-also"></a>こちらもご覧ください

[エラー処理と通知](error-handling-and-notification.md)
