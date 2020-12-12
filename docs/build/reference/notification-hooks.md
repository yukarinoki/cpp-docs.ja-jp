---
description: 詳細については、「通知フック」を参照してください。
title: 通知フック
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, notification hooks
ms.assetid: e9c291ed-2f2d-4319-a171-09800625256f
ms.openlocfilehash: 716d2b31faa71c77ec436662ce00368d15afc4b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209751"
---
# <a name="notification-hooks"></a>通知フック

通知フックは、ヘルパールーチンで次のアクションが実行される直前に呼び出されます。

- ライブラリへの格納されているハンドルが、既に読み込まれているかどうかがチェックされます。

- **LoadLibrary** は、DLL の読み込みを試行するために呼び出されます。

- **GetProcAddress** は、プロシージャのアドレスを取得しようとするために呼び出されます。

- 遅延インポート読み込みサンクに戻ります。

通知フックが有効になっています。

- 通知を受け取る独自の関数を指すように初期化される **__pfnDliNotifyHook2** ポインターの新しい定義を指定します。

   \- または -

- プログラムが遅延読み込みを行う DLL の呼び出しの前に、ポインターをフック関数に設定することによって **__pfnDliNotifyHook2** ます。

通知が **Dlistartprocessing** の場合、フック関数は次を返すことができます。

- NULL

   既定のヘルパーは、DLL の読み込みを処理します。 これは、情報提供のみを目的として呼び出す場合に便利です。

- 関数ポインター

   既定の遅延読み込み処理をバイパスします。 これにより、独自の読み込みハンドラーを指定できます。

通知が **dliNotePreLoadLibrary** の場合、フック関数は次を返すことができます。

- 情報通知のみを必要とする場合は0。

- DLL 自体が読み込まれた場合は、読み込まれた DLL の HMODULE。

通知が **dliNotePreGetProcAddress** の場合、フック関数は次を返すことができます。

- 情報通知のみを必要とする場合は0。

- フック関数がアドレス自体を取得する場合は、インポートされた関数のアドレス。

通知が **dliNoteEndProcessing** の場合、フック関数の戻り値は無視されます。

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

通知は、通知値と共に、 **Delayloadinfo** 構造体をフック関数に渡します。 このデータは、遅延読み込みヘルパールーチンによって使用されるものと同じです。 通知値は、 [構造体と定数の定義](structure-and-constant-definitions.md)で定義されている値のいずれかになります。

## <a name="see-also"></a>関連項目

[エラー処理と通知](error-handling-and-notification.md)
