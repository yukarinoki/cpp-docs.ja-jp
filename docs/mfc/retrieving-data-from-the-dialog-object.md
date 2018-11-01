---
title: ダイアログ オブジェクトからのデータの取得
ms.date: 11/04/2016
helpviewer_keywords:
- dialog boxes [MFC], retrieving user data
- dialog box data [MFC]
- data [MFC], retrieving
- GetDlgItemText method [MFC]
- SetDlgItemText method [MFC]
- SetWindowText method [MFC]
- dialog box data [MFC], retrieving
- retrieving data [MFC]
- user input [MFC], retrieving from MFC dialog boxes
- capturing user input [MFC]
- dialog box controls [MFC], initializing values
- DDX (dialog data exchange) [MFC]
- MFC dialog boxes [MFC], retrieving user input
- data retrieval [MFC], dialog boxes
- data [MFC], dialog boxes
- DDX (dialog data exchange) [MFC], about DDX
- DDX (dialog data exchange) [MFC], retrieving data from Dialog object
- GetWindowText method [MFC]
ms.assetid: bdca2b61-6b53-4c2e-b426-8712c7a38ec0
ms.openlocfilehash: 345a2894693eace5aa464ca3940c785b2da08784
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615130"
---
# <a name="retrieving-data-from-the-dialog-object"></a>ダイアログ オブジェクトからのデータの取得

フレームワークは、ダイアログ ボックスのコントロールの値を初期化し、コントロールから値を取得する簡単な方法を提供します。 手間の手動による方法は、関数を呼び出すには、`SetDlgItemText`と`GetDlgItemText`クラスのメンバー関数`CWnd`windows のコントロールに適用します。 これらの関数でアクセスする各コントロールの値を取得または設定を個別に関数の呼び出し`SetWindowText`と`GetWindowText`します。 フレームワークのアプローチでは、初期化と取得の両方を自動化します。

ダイアログ データ エクス (チェンジ DDX) では、ダイアログ オブジェクト内のダイアログ ボックスとメンバー変数内のコントロール間のデータをより簡単に交換することができます。 この exchange では、両方の方法は機能します。 ダイアログ ボックス内のコントロールを初期化するためにダイアログ オブジェクト内のデータ メンバーの値を設定して、フレームワークは、ダイアログ ボックスが表示されるまでに、コントロールの値を転送は。 いつでも更新できますダイアログのデータ メンバーに、ユーザーが入力したデータ。 その時点では、データ メンバー変数を参照してデータを使用することができます。

ダイアログ データ検証 (DDV) を使用して自動的に検証する ダイアログのコントロールの値を配置することもできます。

DDX ルーチンおよび DDV がで詳細に説明した[ダイアログ データ エクス チェンジと検証](../mfc/dialog-data-exchange-and-validation.md)です。

モーダル ダイアログ ボックスでは、ユーザーが入力したときに、データを取得できます`DoModal`IDOK を返しますが、ダイアログ ボックスの前にオブジェクトが破棄されます。 モードレス ダイアログ ボックスのデータを取得できますダイアログ オブジェクトから、いつでも呼び出すことによって`UpdateData`引数で**TRUE**ダイアログ クラスのメンバー変数にアクセスするとします。 このトピックで詳しく説明については[ダイアログ データ エクス チェンジと検証](../mfc/dialog-data-exchange-and-validation.md)です。

## <a name="see-also"></a>関連項目

[ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)

