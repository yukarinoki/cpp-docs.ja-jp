---
title: ダイアログ オブジェクトからデータを取得する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0ac243333c8dc778486dd18323658f262c6d6610
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33380209"
---
# <a name="retrieving-data-from-the-dialog-object"></a>ダイアログ オブジェクトからのデータの取得
フレームワークは、ダイアログ ボックスのコントロールの値を初期化して、コントロールから値を取得する簡単な方法を提供します。 関数を呼び出すなどの手間がかかりより手動的な方法は、`SetDlgItemText`と`GetDlgItemText`クラスのメンバー関数`CWnd`windows のコントロールに適用されます。 これらの関数でアクセスする各コントロールを設定またはその値を取得する個別に関数を呼び出す`SetWindowText`と`GetWindowText`です。 フレームワークのアプローチでは、初期化と取得の両方を自動化します。  
  
 ダイアログ データ エクス (チェンジ DDX) では、ダイアログ オブジェクト内のダイアログ ボックスとメンバー変数内のコントロールの間でデータをより簡単に交換することができます。 この exchange では、両方の方法は機能します。 ダイアログ ボックスのコントロールを初期化するためにダイアログ オブジェクト内のデータ メンバーの値を設定することができ、フレームワークでは、値に転送コントロール ダイアログ ボックスが表示される前にします。 いつでも更新できますダイアログのデータ メンバー、ユーザーが入力したデータを使用します。 その時点では、データ メンバー変数を参照して、データを使用することができます。  
  
 ダイアログ データ バリデーション (DDV) を使用して自動的に検証するダイアログ コントロールの値を配置することもできます。  
  
 DDX ルーチンおよび DDV がで詳しく説明されている[ダイアログ データ エクス チェンジと検証](../mfc/dialog-data-exchange-and-validation.md)です。  
  
 モーダル ダイアログ ボックスで、ユーザーが入力したときに、データを取得できます`DoModal`返します**IDOK**ダイアログ ボックスの前にオブジェクトが破棄されますが、します。 モードレス ダイアログ ボックスのデータを取得できますダイアログ オブジェクトからいつでも呼び出すことによって`UpdateData`引数と共に**TRUE**ダイアログ クラスのメンバー変数にアクセスしています。 このトピックはで詳しく説明[ダイアログ データ エクス チェンジと検証](../mfc/dialog-data-exchange-and-validation.md)です。  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)

