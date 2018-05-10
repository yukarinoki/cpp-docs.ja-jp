---
title: メンバー変数 (Visual C) の追加 |Microsoft ドキュメント
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
ms.openlocfilehash: fa2a8ef8f7bcdc2d90893acdad98705c9588a5d5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="adding-a-member-variable--visual-c"></a>メンバー変数の追加 (Visual C++)
クラス ビューを使用してクラスにメンバー変数を追加することができます。 メンバー変数には、いずれかを指定できる[データ交換とデータの検証](../mfc/dialog-data-exchange-and-validation.md)、汎用的な可能性があるか。 データ メンバー変数のウィザードは具体的には関連の情報を取得し、要素を挿入する適切な場所にあるソース ファイルで使用するよう設計されています。 メンバー変数を追加することができます、[ダイアログ エディター](../windows/dialog-editor.md)で[リソース ビュー](../windows/resource-view-window.md)、またはから[クラス ビュー](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)です。  
  
> [!NOTE]
>  デザインすると、ダイアログ ボックスを実装するには、した方が、ダイアログ ボックスを使用する方が効率的エディター ダイアログ ボックス コントロールを追加して、そのコントロールのメンバー変数を実装するためにします。  
  
### <a name="to-add-a-member-variable-for-a-dialog-control-in-resource-view-using-the-add-member-variable-wizard"></a>メンバー変数の追加ウィザードを使用してリソース ビューでダイアログ コントロールのメンバー変数を追加するには  
  
1.  リソース ビュー で、プロジェクト ノードと、プロジェクトのダイアログ ボックスの一覧を表示するダイアログのノードを展開します。  
  
2.  ダイアログ エディターで開くメンバー変数を追加する ダイアログ ボックスをダブルクリックします。  
  
3.  ダイアログ エディターでの表示 ダイアログ ボックスで、メンバー変数を追加するコントロールを右クリックします。  
  
4.  ショートカット メニューをクリックして**変数の追加**を表示する、[変数の追加メンバー ウィザード](../ide/add-member-variable-wizard.md)です。  
  
    > [!NOTE]
    >  既定値が既にで提供されている**コントロール ID**です。  
  
5.  ウィザードの各ボックスに情報を入力します。 参照してください[ダイアログ ボックス コントロールおよび変数の型](../ide/dialog-box-controls-and-variable-types.md)詳細についてはします。  
  
6.  をクリックして**完了**をプロジェクトに定義と実装コードを追加し、ウィザードを閉じます。  
  
### <a name="to-add-a-member-variable-from-class-view-using-the-add-member-variable-wizard"></a>メンバー変数の追加ウィザードを使用して、クラス ビューから、メンバー変数を追加するには  
  
1.  [クラス ビュー](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)クラスを表示する、プロジェクトのプロジェクト ノードを展開します。  
  
2.  変数を追加するクラスを右クリックします。  
  
3.  ショートカット メニューをクリックして**追加**、順にクリック**変数の追加**メンバー変数の追加ウィザードを表示します。  
  
4.  ウィザードの各ボックスに情報を入力します。 参照してください[変数の追加メンバー ウィザード](../ide/add-member-variable-wizard.md)詳細についてはします。  
  
5.  をクリックして**完了**をプロジェクトに定義と実装コードを追加し、ウィザードを閉じます。  
  
## <a name="see-also"></a>関連項目  
 [コード ウィザードによる機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [クラスの追加](../ide/adding-a-class-visual-cpp.md)   
 [メンバー関数の追加](../ide/adding-a-member-function-visual-cpp.md)   
 [MFC メッセージ ハンドラー](../mfc/reference/adding-an-mfc-message-handler.md)   
 [クラス各部へ](../ide/navigating-the-class-structure-visual-cpp.md)