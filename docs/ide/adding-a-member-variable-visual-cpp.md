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
ms.openlocfilehash: dade9987358c1c160dffd0221b0421b4fab92c24
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43687643"
---
# <a name="adding-a-member-variable--visual-c"></a>メンバー変数の追加 (Visual C++)
クラス ビューを使用して、クラスにメンバー変数を追加することができます。 メンバー変数は、[データ交換とデータの入力規則](../mfc/dialog-data-exchange-and-validation.md)に使用するか、一般にすることができます。 データ メンバー変数ウィザードは、具体的には関連情報を取得して、適切な場所のソース ファイル内に要素を挿入するために設計されています。 [リソース ビュー](../windows/resource-view-window.md)の[ダイアログ エディター](../windows/dialog-editor.md)、または[クラス ビュー](/visualstudio/ide/viewing-the-structure-of-code)からメンバー変数を追加できます。  
  
> [!NOTE]
>  ダイアログ ボックスを設計および実装しているときに、ダイアログ エディターを使用して、ダイアログ ボックス コントロールを追加し、コントロールのメンバー変数を実装すると効率的である場合があります。  
  
### <a name="to-add-a-member-variable-for-a-dialog-control-in-resource-view-using-the-add-member-variable-wizard"></a>メンバー変数の追加ウィザードを使用して、リソース ビューにダイアログ コントロールのメンバー変数を追加するには  
  
1.  リソース ビューでプロジェクト ノードとダイアログ ノードを展開して、プロジェクトのダイアログ ボックスのリストを表示します。  
  
2.  メンバー変数を追加するダイアログ ボックスをダブルクリックして、ダイアログ エディターで開きます。  
  
3.  ダイアログ エディターに表示されたダイアログ ボックスで、メンバー変数を追加するコントロールを右クリックします。  
  
4.  ショートカット メニューで、**[変数の追加]** をクリックして[メンバー変数の追加ウィザード](../ide/add-member-variable-wizard.md)を表示します。  
  
    > [!NOTE]
    >  既定値が既に**コントロール ID** に提供されています。  
  
5.  適切なウィザード ボックスに情報を指定します。 詳細については、「[Dialog Box Controls and Variable Types](../ide/dialog-box-controls-and-variable-types.md)」 (ダイアログ ボックス コントロールおよび変数の型) を参照してください。  
  
6.  **[完了]** をクリックして、プロジェクトに定義と実装コードを追加し、ウィザードを閉じます。  
  
### <a name="to-add-a-member-variable-from-class-view-using-the-add-member-variable-wizard"></a>メンバー変数の追加ウィザードを使用して、クラス ビューからメンバー変数を追加するには  
  
1.  [クラス ビュー](/visualstudio/ide/viewing-the-structure-of-code)でプロジェクト ノードを展開して、プロジェクト内のクラスを表示します。  
  
2.  変数を追加するクラスを右クリックします。  
  
3.  ショートカット メニューで、**[追加]**、**[変数の追加]** の順にクリックして、メンバー変数の追加ウィザードを表示します。  
  
4.  適切なウィザード ボックスに情報を指定します。 詳細については、「[Add Member Variable Wizard](../ide/add-member-variable-wizard.md)」 (メンバー変数の追加ウィザード) を参照してください。  
  
5.  **[完了]** をクリックして、プロジェクトに定義と実装コードを追加し、ウィザードを閉じます。  
  
## <a name="see-also"></a>参照  
 [コード ウィザードを使用した機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [クラスの追加](../ide/adding-a-class-visual-cpp.md)   
 [メンバー関数の追加](../ide/adding-a-member-function-visual-cpp.md)   
 [MFC メッセージ ハンドラー](../mfc/reference/adding-an-mfc-message-handler.md)   
 [クラス各部へのジャンプ](../ide/navigating-the-class-structure-visual-cpp.md)