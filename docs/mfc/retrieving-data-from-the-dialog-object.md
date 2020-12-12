---
description: 詳細については、「ダイアログオブジェクトからのデータの取得」を参照してください。
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
ms.openlocfilehash: 823006b7b892c8e6476d007eb5cc13fb1386458e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218044"
---
# <a name="retrieving-data-from-the-dialog-object"></a>ダイアログ オブジェクトからのデータの取得

フレームワークを使用すると、ダイアログボックス内のコントロールの値を初期化したり、コントロールから値を取得したりするための簡単な方法が提供されます。 より面倒な手動による方法は、 `SetDlgItemText` `GetDlgItemText` `CWnd` コントロールウィンドウに適用されるクラスの関数やメンバー関数などの関数を呼び出すことです。 これらの関数を使用すると、それぞれのコントロールに個別にアクセスして、値を設定または取得し、やなどの関数を呼び出すことができ `SetWindowText` `GetWindowText` ます。 このフレームワークのアプローチは、初期化と取得の両方を自動化します。

ダイアログデータエクスチェンジ (DDX) を使用すると、ダイアログボックス内のコントロールとダイアログオブジェクトのメンバー変数との間で、より簡単にデータを交換できます。 この交換は両方の方法で機能します。 ダイアログボックス内のコントロールを初期化するには、ダイアログオブジェクトのデータメンバーの値を設定します。ダイアログボックスが表示される前に、フレームワークによって値がコントロールに転送されます。 その後、ユーザーが入力したデータを使用してダイアログデータメンバーをいつでも更新できます。 その時点で、データメンバー変数を参照してデータを使用できます。

ダイアログデータ検証 (DDV) を使用して自動的に検証されるダイアログコントロールの値を設定することもできます。

DDX と DDV の詳細については [、「ダイアログデータエクスチェンジと検証](../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

モーダルダイアログボックスの場合は、が IDOK を返したときに、 `DoModal` ダイアログオブジェクトが破棄される前にユーザーが入力したデータを取得できます。 モードレスダイアログボックスの場合は、引数 TRUE を指定してを呼び出し、 `UpdateData` ダイアログクラスメンバー変数にアクセスすることで、いつでもダイアログオブジェクトからデータを取得できます。 このトピックの詳細については [、「ダイアログデータエクスチェンジと検証](../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

## <a name="see-also"></a>関連項目

[MFC でのダイアログ ボックスの操作](../mfc/life-cycle-of-a-dialog-box.md)
