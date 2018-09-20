---
title: ダイアログ データ検証 |Microsoft Docs
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
ms.openlocfilehash: 83c1208d3001739ca78186972c629ea8a094c8d8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430892"
---
# <a name="dialog-data-validation"></a>ダイアログ データ検証

例で示すように、DDV 関数の呼び出しでデータ交換だけでなく検証を指定できます[ダイアログ データ エクス チェンジ](../mfc/dialog-data-exchange.md)します。 `DDV_MaxChars`呼び出しの例では、テキスト ボックス コントロールに入力した文字列が 20 文字より長くしないことを検証します。 検証が失敗すると、データを再入力できるように、問題のあるコントロールにフォーカスを設定、DDV 関数は通常メッセージ ボックスにユーザーを警告します。 同じコントロールの DDX 関数後すぐに、特定のコントロールの DDV 関数を呼び出す必要があります。

独自のカスタムの DDX ルーチンおよび DDV ルーチンを定義することもできます。 これと DDX ルーチンおよび DDV の他の側面の詳細については、次を参照してください。 [MFC テクニカル ノート 26](../mfc/tn026-ddx-and-ddv-routines.md)します。

[追加メンバー変数のウィザード](../ide/add-member-variable-wizard.md)DDX のすべてを記述および DDV 呼び出しがデータ マップにできます。

## <a name="see-also"></a>関連項目

[ダイアログ データ エクスチェンジとダイアログ データ検証](../mfc/dialog-data-exchange-and-validation.md)<br/>
[ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[ダイアログ データ エクスチェンジ](../mfc/dialog-data-exchange.md)

