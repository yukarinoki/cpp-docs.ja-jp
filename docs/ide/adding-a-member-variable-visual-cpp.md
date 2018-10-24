---
title: メンバー変数の追加 (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.classes.member.variable
dev_langs:
- C++
helpviewer_keywords:
- member variables, adding
- member variables
ms.assetid: 437783bd-8eb4-4508-8b73-7380116e9d71
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec9409067793da0e0a89be668f57e86588bdc2d8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46447324"
---
# <a name="adding-a-member-variable--visual-c"></a>メンバー変数の追加 (Visual C++)

クラス ビューを使用して、クラスにメンバー変数を追加することができます。 メンバー変数は、[データ交換とデータの入力規則](../mfc/dialog-data-exchange-and-validation.md)に使用するか、一般にすることができます。 データ メンバー変数ウィザードは、具体的には関連情報を取得して、適切な場所のソース ファイル内に要素を挿入するために設計されています。 [リソース ビュー](../windows/resource-view-window.md)の[ダイアログ エディター](../windows/dialog-editor.md)、または[クラス ビュー](/visualstudio/ide/viewing-the-structure-of-code)からメンバー変数を追加できます。

> [!NOTE]
>  ダイアログ ボックスを設計および実装しているときに、ダイアログ エディターを使用して、ダイアログ ボックス コントロールを追加し、コントロールのメンバー変数を実装すると効率的である場合があります。

### <a name="to-add-a-member-variable-for-a-dialog-control-in-resource-view-using-the-add-member-variable-wizard"></a>メンバー変数の追加ウィザードを使用して、リソース ビューにダイアログ コントロールのメンバー変数を追加するには

1. リソース ビューでプロジェクト ノードとダイアログ ノードを展開して、プロジェクトのダイアログ ボックスのリストを表示します。

1. メンバー変数を追加するダイアログ ボックスをダブルクリックして、ダイアログ エディターで開きます。

1. ダイアログ エディターに表示されたダイアログ ボックスで、メンバー変数を追加するコントロールを右クリックします。

1. ショートカット メニューで、**[変数の追加]** をクリックして[メンバー変数の追加ウィザード](../ide/add-member-variable-wizard.md)を表示します。

   > [!NOTE]
   > 既定値が既に**コントロール ID** に提供されています。

1. 適切なウィザード ボックスに情報を指定します。 詳細については、「[Dialog Box Controls and Variable Types](../ide/dialog-box-controls-and-variable-types.md)」 (ダイアログ ボックス コントロールおよび変数の型) を参照してください。

1. **[完了]** をクリックして、プロジェクトに定義と実装コードを追加し、ウィザードを閉じます。

### <a name="to-add-a-member-variable-from-class-view-using-the-add-member-variable-wizard"></a>メンバー変数の追加ウィザードを使用して、クラス ビューからメンバー変数を追加するには

1. [クラス ビュー](/visualstudio/ide/viewing-the-structure-of-code)でプロジェクト ノードを展開して、プロジェクト内のクラスを表示します。

1. 変数を追加するクラスを右クリックします。

1. ショートカット メニューで、**[追加]**、**[変数の追加]** の順にクリックして、メンバー変数の追加ウィザードを表示します。

1. 適切なウィザード ボックスに情報を指定します。 詳細については、「[Add Member Variable Wizard](../ide/add-member-variable-wizard.md)」 (メンバー変数の追加ウィザード) を参照してください。

1. **[完了]** をクリックして、プロジェクトに定義と実装コードを追加し、ウィザードを閉じます。

## <a name="see-also"></a>参照

[コード ウィザードを使用した機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)<br>
[クラスの追加](../ide/adding-a-class-visual-cpp.md)<br>
[メンバー関数の追加](../ide/adding-a-member-function-visual-cpp.md)<br>
[MFC メッセージ ハンドラー](../mfc/reference/adding-an-mfc-message-handler.md)<br>
[クラス各部へのジャンプ](../ide/navigating-the-class-structure-visual-cpp.md)