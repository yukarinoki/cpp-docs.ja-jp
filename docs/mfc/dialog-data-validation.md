---
title: ダイアログ データ バリデーション
ms.date: 11/04/2016
helpviewer_keywords:
- validating data [MFC], message boxes
- data validation [MFC], dialog boxes
- dialog boxes [MFC], validating data
- validating data [MFC], dialog box data entry
- DDV (dialog data validation) [MFC]
- data validation [MFC], message boxes
ms.assetid: f070c309-2044-4ff2-8c92-1ec1ea84af58
ms.openlocfilehash: 99540214d1b903c66d350145c08ab657d12ef8f7
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616755"
---
# <a name="dialog-data-validation"></a>ダイアログ データ バリデーション

「[ダイアログデータエクスチェンジ](dialog-data-exchange.md)」の例に示すように、DDV 関数を呼び出すことにより、データ交換に加えて検証を指定できます。 この `DDV_MaxChars` 例の呼び出しは、テキストボックスコントロールに入力された文字列が20文字を超えていないことを検証します。 通常、DDV 関数は、検証に失敗した場合にメッセージボックスを使用してユーザーに警告し、ユーザーがデータを再入力できるように、問題のあるコントロールにフォーカスを移します。 特定のコントロールの DDV 関数は、同じコントロールの DDX 関数の直後に呼び出す必要があります。

独自のカスタム DDX ルーチンおよび DDV ルーチンを定義することもできます。 DDX および DDV のその他の側面の詳細については、「 [MFC テクニカルノート 26](tn026-ddx-and-ddv-routines.md)」を参照してください。

[メンバー変数の追加ウィザード](../ide/add-member-variable-wizard.md)では、データマップ内のすべての DDX 呼び出しと DDV 呼び出しが書き込まれます。

## <a name="see-also"></a>関連項目

[ダイアログ データ エクスチェンジとダイアログ データ検証](dialog-data-exchange-and-validation.md)<br/>
[MFC でのダイアログ ボックスの操作](life-cycle-of-a-dialog-box.md)<br/>
[ダイアログ データ エクスチェンジ](dialog-data-exchange.md)
