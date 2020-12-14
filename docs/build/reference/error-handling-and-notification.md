---
description: 詳細については、「エラー処理と通知」を参照してください。
title: エラー処理と通知
ms.date: 11/04/2016
helpviewer_keywords:
- error handling, and notification
ms.assetid: b621cf60-d869-451a-b05e-dc86d78addaa
ms.openlocfilehash: 234d50d0b4a7e8b81874d1926ac056f8cba23376
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200989"
---
# <a name="error-handling-and-notification"></a>エラー処理と通知

エラー処理と通知の詳細については、「 [ヘルパー関数](understanding-the-helper-function.md)について」を参照してください。

フック関数の詳細については、「 [構造体と定数の定義](structure-and-constant-definitions.md)」を参照してください。

プログラムが遅延読み込みされた Dll を使用している場合は、プログラムの実行中に発生したエラーによってハンドルされない例外が発生するため、エラーを確実に処理する必要があります。 エラー処理は、次の2つの部分で構成されます。

フックによる復旧。
障害発生時にコードで回復する必要がある場合、または代替ライブラリやルーチンを提供する必要がある場合は、その状況を提供または解決できるヘルパー関数にフックを提供できます。 フックルーチンは適切な値を返す必要があるため、処理を続行 (HINSTANCE または FARPROC) するか、0を指定して例外をスローする必要があることを示します。 また、独自の例外をスローし **たり、** フックの外にしたりすることもできます。 通知フックとエラーフックがあります。

例外を使用したレポート。
エラーの処理に必要なものがすべてプロシージャを中止する場合は、ユーザーコードが例外を処理できる限り、フックは必要ありません。

次のトピックでは、エラー処理と通知について説明します。

- [通知フック](notification-hooks.md)

- [エラーフック](failure-hooks.md)

- [例外](exceptions-c-cpp.md)

## <a name="see-also"></a>関連項目

[リンカーによる Delay-Loaded Dll のサポート](linker-support-for-delay-loaded-dlls.md)
