---
title: ダイアログ クラスの作成
ms.date: 09/06/2019
helpviewer_keywords:
- dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- files [MFC], creating
- dialog classes [MFC], Add Class Wizard
- dialog classes [MFC], creating
ms.assetid: d5321741-da41-47a8-bb1c-6a0e8b28c4c1
ms.openlocfilehash: 424d18196063456245e2a4841b42e6e447bded17
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907324"
---
# <a name="creating-your-dialog-class"></a>ダイアログ クラスの作成

プログラム内の各ダイアログボックスで、ダイアログリソースを操作するための新しいダイアログクラスを作成します。

[クラスを追加](../ide/adding-a-class-visual-cpp.md)すると、新しいダイアログクラスを作成する方法が説明されます。 [クラスウィザード](reference/mfc-class-wizard.md)を使用してダイアログクラスを作成すると、指定した .h ファイルと .cpp ファイルに次の項目が書き込まれます。

.H ファイルで、次のようにします。

- ダイアログクラスのクラス宣言。 クラスは、 [CDialog](../mfc/reference/cdialog-class.md)から派生します。

.Cpp ファイルで、次のようにします。

- クラスのメッセージマップ。

- ダイアログボックスの標準コンストラクター。

- [DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange)メンバー関数のオーバーライド。 この関数を編集します。 ダイアログデータエクスチェンジおよび検証機能に使用されます。詳細については、「[ダイアログデータエクスチェンジと検証](../mfc/dialog-data-exchange-and-validation.md)」を参照してください。

## <a name="see-also"></a>関連項目

[コード ウィザードによるダイアログ クラスの作成](../mfc/creating-a-dialog-class-with-code-wizards.md)<br/>
[ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)
