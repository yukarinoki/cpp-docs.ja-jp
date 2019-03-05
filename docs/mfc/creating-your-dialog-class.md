---
title: ダイアログ クラスの作成
ms.date: 11/04/2016
helpviewer_keywords:
- dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- files [MFC], creating
- dialog classes [MFC], Add Class Wizard
- dialog classes [MFC], creating
ms.assetid: d5321741-da41-47a8-bb1c-6a0e8b28c4c1
ms.openlocfilehash: bacedc49fcdabdd5dc7fb0f392a66afd3baadd06
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57326401"
---
# <a name="creating-your-dialog-class"></a>ダイアログ クラスの作成

プログラム内の各ダイアログ ボックスには、ダイアログ リソースを使用する新しいダイアログ クラスを作成します。

[クラスの追加](../ide/adding-a-class-visual-cpp.md)ダイアログの新しいクラスを作成する方法について説明します。 次のものはそのクラスの追加ウィザードとダイアログ クラスを作成するときに、します。H とします。CPP ファイルを指定する:

の。H ファイル:

- ダイアログ クラスのクラス宣言します。 派生したクラスは[CDialog](../mfc/reference/cdialog-class.md)します。

の。CPP ファイル:

- クラスのメッセージ マップです。

- ダイアログ ボックスの標準コンス トラクターです。

- オーバーライド、 [DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange)メンバー関数。 この関数を編集します。 後で説明したようダイアログ データの交換と検証の機能の使用されて[ダイアログ データ エクス チェンジと検証](../mfc/dialog-data-exchange-and-validation.md)です。

## <a name="see-also"></a>関連項目

[コード ウィザードによるダイアログ クラスの作成](../mfc/creating-a-dialog-class-with-code-wizards.md)<br/>
[ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)
