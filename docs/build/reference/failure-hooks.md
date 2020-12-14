---
description: 詳細については、「エラーフック」を参照してください。
title: エラー フック
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, failure hooks
ms.assetid: 12bb303b-ffe6-4471-bffe-9ef4f8bb2d30
ms.openlocfilehash: a0e74e3413fc81505941dd6f4545988a0d39436f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200729"
---
# <a name="failure-hooks"></a>エラー フック

エラーフックは、 [通知フック](notification-hooks.md)と同じ方法で有効になります。 フックルーチンは、処理を続行できるように適切な値を返す必要があります (HINSTANCE または FARPROC)。0の場合は、例外がスローされることを示します。

ユーザー定義関数を参照するポインター変数は次のとおりです。

```
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}
ExternC
PfnDliHook   __pfnDliFailureHook2;
```

**Delayloadinfo** 構造体には、の値を含め、エラーを正確に報告するために必要なすべての関連データが含まれてい `GetLastError` ます。

通知が **Dlifailloadlib** の場合、フック関数は次を返すことができます。

- エラーを処理できない場合は0。

- HMODULE。エラーフックによって問題が修正され、ライブラリ自体が読み込まれた場合。

通知が **Dlifailgetproc** の場合、フック関数は次を返すことができます。

- エラーを処理できない場合は0。

- エラーフックがアドレス自体を取得するのに成功した場合は、有効な proc address (import 関数のアドレス)。

## <a name="see-also"></a>関連項目

[エラー処理と通知](error-handling-and-notification.md)
