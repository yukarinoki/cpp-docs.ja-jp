---
title: エラー処理と通知 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- error handling, and notification
ms.assetid: b621cf60-d869-451a-b05e-dc86d78addaa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e2edec23da89766a45545566b0a689001d3ca75f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373219"
---
# <a name="error-handling-and-notification"></a>エラー処理と通知
エラー処理と通知の詳細については、次を参照してください。[ヘルパー関数について](understanding-the-helper-function.md)です。  
  
 用のフック関数の詳細については、次を参照してください。[構造体と定数定義](../../build/reference/structure-and-constant-definitions.md)です。  
  
 プログラムでは、遅延読み込みされた Dll を使用する場合、プログラムの実行中に発生する障害が発生した未処理の例外から堅牢エラーを処理にする必要があります。 エラー処理は、2 つの部分で構成されます。  
  
 フックによる回復します。  
 コードは、回復または失敗した場合に、別のライブラリやルーチンを提供する必要があるを場合を指定したり、問題を解決できるヘルパー関数をフックを指定できます。 フック ルーチンの必要性を処理できるように、適切な値を返すことが続行する (HINSTANCE か FARPROC) または 0 で、例外をスローすることを示します。 独自の例外をスローする可能性がありますもまたは**longjmp**フック外です。 通知フックとエラー フックがあります。  
  
 例外を使用してレポートを作成します。  
 プロシージャを中止するすべてのエラーを処理するために必要な場合は、用のフックは必要ありません、ユーザー コードが例外を処理できる限り、します。  
  
 次のトピックでは、エラー処理と通知について説明します。  
  
-   [通知フック](../../build/reference/notification-hooks.md)  
  
-   [エラー フック](../../build/reference/failure-hooks.md)  
  
-   [例外](../../build/reference/exceptions-c-cpp.md)  
  
## <a name="see-also"></a>関連項目  
 [リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)