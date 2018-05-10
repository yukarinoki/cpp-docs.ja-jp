---
title: オーバーライドする仮想関数 (Visual C) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.virtualfunc.override
dev_langs:
- C++
helpviewer_keywords:
- virtual functions, overriding
- base classes, overriding virtual functions defined in
- Properties window, overriding virtual functions in
ms.assetid: 2d8c76f2-7a6b-4c9c-8de5-4282ce7755b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d8580d27442b0cae7e343a568beaa9aeae500461
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="overriding-a-virtual-function-visual-c"></a>仮想関数のオーバーライド (Visual C++)
Visual Studio の基本クラスで定義されている仮想関数をオーバーライドできます[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。  
  
### <a name="to-override-a-virtual-function-in-the-properties-window"></a>[プロパティ] ウィンドウで仮想関数をオーバーライドするには  
  
1.  クラス ビューでは、クラスをクリックします。  
  
2.  [プロパティ] ウィンドウ、**オーバーライド**ボタンをクリックします。  
  
    > [!NOTE]
    >  **オーバーライド**クラス ビュー、または、ソース ウィンドウ内をクリックすると、いずれかのクラス名を選択すると、ボタンは使用できます。  
  
     左の列には、仮想関数が一覧表示します。 場合も、仮想関数の名前は、右側の列が表示されたら、上書き既に実装されています。  
  
3.  関数は、関数の名前を表示する [プロパティ] ウィンドウで、右側の列のセルをクリックし、上書きを持たない場合はオーバーライド\<追加 >*FuncName*です。  
  
4.  関数のスタブ コードを追加する推奨される名前をクリックします。  
  
5.  オーバーライドする関数を編集するには、クラス ビュー内の関数の名前をダブルクリックし、ソース ウィンドウ内のコードを編集します。  
  
 上書きを削除するに、右側の列内のオーバーライド関数名をクリックし、選択\<削除 >*FuncName*です。 関数のコードをコメント アウトします。  
  
## <a name="see-also"></a>関連項目  
 [コード ウィザードによる機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [クラスの追加](../ide/adding-a-class-visual-cpp.md)   
 [メンバー関数の追加](../ide/adding-a-member-function-visual-cpp.md)   
 [メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md)   
 [MFC メッセージ ハンドラー](../mfc/reference/adding-an-mfc-message-handler.md)   
 [クラス各部へ](../ide/navigating-the-class-structure-visual-cpp.md)