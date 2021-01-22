---
description: 詳細については、「遅延読み込みエラーフック」を参照してください。
title: エラー フック
ms.date: 01/19/2021
helpviewer_keywords:
- delayed loading of DLLs, failure hooks
ms.openlocfilehash: 46cec6c66169ebe589bb5f0c912b2d8239e69da1
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667181"
---
# <a name="failure-hooks"></a>エラー フック

エラーフックは、 [通知フック](notification-hooks.md)と同じ方法で有効になります。 フックルーチンは、処理を続行できるように適切な値を返す必要があり `HINSTANCE` ます (または)。0の場合は、例外がスローされることを `FARPROC` 示します。

ユーザー定義関数を参照するポインター変数は次のとおりです。

```C
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}
ExternC
PfnDliHook   __pfnDliFailureHook2;
```

構造体には、の **`DelayLoadInfo`** 値を含め、エラーを正確に報告するために必要なすべての関連データが含まれてい `GetLastError` ます。

通知がの場合 **`dliFailLoadLib`** 、フック関数は次を返すことができます。

- エラーを処理できない場合は0。

- `HMODULE`エラーフックによって問題が修正され、ライブラリ自体が読み込まれた場合は。

通知がの場合 **`dliFailGetProc`** 、フック関数は次を返すことができます。

- エラーを処理できない場合は0。

- エラーフックがアドレス自体を取得するのに成功した場合は、有効な proc address (import 関数のアドレス)。

## <a name="see-also"></a>こちらもご覧ください

[エラー処理と通知](error-handling-and-notification.md)
