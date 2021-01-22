---
title: エラー処理と通知
description: 詳細については、「DLL 遅延読み込みエラー処理と通知」を参照してください。
ms.date: 01/19/2021
helpviewer_keywords:
- error handling, and notification
ms.openlocfilehash: a0161814a07bd5bbedbaa6d13c7c32cd3aeab559
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "98666954"
---
# <a name="error-handling-and-notification"></a>エラー処理と通知

プログラムが遅延読み込みされた Dll を使用している場合、プログラムの実行中に発生したエラーによってハンドルされない例外が発生するため、エラーを確実に処理する必要があります。 エラー処理は、フックを使用した復旧と、例外によるレポートの2つの部分で構成されます。

DLL 遅延読み込みエラー処理と通知の詳細については、「 [ヘルパー関数につい](understanding-the-helper-function.md)て」を参照してください。

フック関数の詳細については、「 [構造体と定数の定義](structure-and-constant-definitions.md)」を参照してください。

## <a name="recovery-through-a-hook"></a>フックによる復旧

コードで障害が発生したときに回復するか、別のライブラリまたはルーチンを提供することが必要になる場合があります。 代替コードを提供できるヘルパー関数にフックを提供したり、状況を修正したりすることができます。 フックルーチンは、処理を続行できるように適切な値を返す必要があり `HINSTANCE` ます (または `FARPROC` )。 または、0を返して、例外をスローする必要があることを示します。 また、独自の例外 `longjmp` をスローしたり、フックから除外したりすることもできます。 通知フックとエラーフックがあります。

## <a name="reporting-via-an-exception"></a>例外によるレポート

エラーを処理するために必要なものがすべてプロシージャを中止するだけの場合は、ユーザーコードが例外を処理できる限り、フックは必要ありません。

次の記事では、エラー処理と通知について説明します。

- [通知フック](notification-hooks.md)

- [エラー フック](failure-hooks.md)

- [DLL 遅延読み込みの例外コード](exceptions-c-cpp.md)

## <a name="see-also"></a>こちらもご覧ください

[リンカーによる DLL の遅延読み込み](linker-support-for-delay-loaded-dlls.md)
