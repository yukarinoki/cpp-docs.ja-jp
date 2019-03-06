---
title: エラー処理と通知
ms.date: 11/04/2016
helpviewer_keywords:
- error handling, and notification
ms.assetid: b621cf60-d869-451a-b05e-dc86d78addaa
ms.openlocfilehash: 7aae4d68b272a6c12233f283d4b263648062b7c1
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57418946"
---
# <a name="error-handling-and-notification"></a>エラー処理と通知

エラー処理と通知の詳細については、次を参照してください。[ヘルパー関数について](understanding-the-helper-function.md)します。

用のフック関数の詳細については、次を参照してください。[構造体と定数定義](../../build/reference/structure-and-constant-definitions.md)します。

プログラムでは、Dll の遅延読み込みを使用する場合、プログラムの実行中に発生する障害が発生した未処理の例外から確実エラーを処理にする必要があります。 エラー処理は、2 つの部分で構成されます。

フックによる復旧します。
を、コードが回復または失敗した場合、代替のライブラリやルーチンを提供する必要がある場合は、ヘルパー関数を指定したり、問題を解決するフックを指定できます。 (HINSTANCE または FARPROC) を行うフックの日常的なニーズを処理できるように、適切な値を返すまたは 0 に、例外をスローする必要があります。 独自の例外をスローする可能性がありますもまたは**longjmp**フック外です。 通知フックとエラー フックがあります。

例外を使用してレポートを作成します。
プロシージャを中止するすべてのエラーを処理するために必要な場合は、フックは必要ありません、ユーザー コードが例外を処理できる限り、します。

次のトピックでは、エラー処理と通知について説明します。

- [通知フック](../../build/reference/notification-hooks.md)

- [エラー フック](../../build/reference/failure-hooks.md)

- [例外](../../build/reference/exceptions-c-cpp.md)

## <a name="see-also"></a>関連項目

[リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)
