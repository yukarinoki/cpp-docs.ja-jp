---
title: ダイアログ データ バリデーション |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- validating data [MFC], message boxes
- data validation [MFC], dialog boxes
- dialog boxes [MFC], validating data
- validating data [MFC], dialog box data entry
- DDV (dialog data validation) [MFC]
- data validation [MFC], message boxes
ms.assetid: f070c309-2044-4ff2-8c92-1ec1ea84af58
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 229b4a5ffb32f4a167dcc8393a269bbb2e35b500
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="dialog-data-validation"></a>ダイアログ データ検証
例に示すように、DDV 関数を呼び出すことによりデータ交換だけでなく検証を指定できます[ダイアログ データ エクス チェンジ](../mfc/dialog-data-exchange.md)です。 `DDV_MaxChars`呼び出しの例では、テキスト ボックス コントロールに入力した文字列が 20 文字を超えていないことを検証します。 DDV 関数は、通常、ユーザーに警告、メッセージ ボックスで検証が失敗するし、データを再入力できるように、問題のあるコントロールにフォーカスを設定します。 特定のコントロールの DDV 関数は、同じコントロールに対して、DDX 関数の直後後に呼び出される必要があります。  
  
 独自のカスタムの DDX ルーチンおよび DDV ルーチンを定義することもできます。 これと DDX ルーチンおよび DDV の他の側面の詳細については、次を参照してください。 [MFC テクニカル ノート 26](../mfc/tn026-ddx-and-ddv-routines.md)です。  
  
 [変数の追加メンバー ウィザード](../ide/add-member-variable-wizard.md)をすべて、DDX の記述および DDV 呼び出しがデータ マップにします。  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ データ交換と検証](../mfc/dialog-data-exchange-and-validation.md)   
 [ダイアログ ボックスのライフ サイクル](../mfc/life-cycle-of-a-dialog-box.md)   
 [ダイアログ データ エクスチェンジ](../mfc/dialog-data-exchange.md)

