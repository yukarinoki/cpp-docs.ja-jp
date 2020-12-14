---
description: 詳細については、「ダイアログクラスの作成」を参照してください。
title: ダイアログ クラスの作成
ms.date: 09/06/2019
helpviewer_keywords:
- dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- files [MFC], creating
- dialog classes [MFC], Add Class Wizard
- dialog classes [MFC], creating
ms.assetid: d5321741-da41-47a8-bb1c-6a0e8b28c4c1
ms.openlocfilehash: d135d6acaefbc73f435e48db8f72add7081fdac2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309447"
---
# <a name="creating-your-dialog-class"></a>ダイアログ クラスの作成

プログラム内の各ダイアログボックスで、ダイアログリソースを操作するための新しいダイアログクラスを作成します。

[クラスを追加](../ide/adding-a-class-visual-cpp.md) すると、新しいダイアログクラスを作成する方法が説明されます。 [クラスウィザード](reference/mfc-class-wizard.md)を使用してダイアログクラスを作成すると、指定した .h ファイルと .cpp ファイルに次の項目が書き込まれます。

.H ファイルで、次のようにします。

- ダイアログクラスのクラス宣言。 クラスは、 [CDialog](reference/cdialog-class.md)から派生します。

.Cpp ファイルで、次のようにします。

- クラスのメッセージマップ。

- ダイアログボックスの標準コンストラクター。

- [DoDataExchange](reference/cwnd-class.md#dodataexchange)メンバー関数のオーバーライド。 この関数を編集します。 ダイアログデータエクスチェンジおよび検証機能に使用されます。詳細については、「 [ダイアログデータエクスチェンジと検証](dialog-data-exchange-and-validation.md)」を参照してください。

## <a name="see-also"></a>関連項目

[コードウィザードを使用したダイアログクラスの作成](creating-a-dialog-class-with-code-wizards.md)<br/>
[MFC でのダイアログ ボックスの操作](life-cycle-of-a-dialog-box.md)
