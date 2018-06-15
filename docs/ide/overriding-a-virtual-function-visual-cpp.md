---
title: 仮想関数のオーバーライド (Visual C++) | Microsoft Docs
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
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "33337744"
---
# <a name="overriding-a-virtual-function-visual-c"></a>仮想関数のオーバーライド (Visual C++)
Visual Studio の[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)では、基本クラスで定義されている仮想関数をオーバーライドすることができます。  
  
### <a name="to-override-a-virtual-function-in-the-properties-window"></a>プロパティ ウィンドウで仮想関数をオーバーライドするには  
  
1.  クラス ビューで、クラスをクリックします。  
  
2.  プロパティ ウィンドウで、**[オーバーライド]** ボタンをクリックします。  
  
    > [!NOTE]
    >  **[オーバーライド]** ボタンは、クラス ビューでクラス名を選択したとき、またはソース ウィンドウ内をクリックしたときに使用できます。  
  
     左の列には仮想関数が一覧表示されます。 右の列にも仮想関数の名前が表示される場合は、既にオーバーライドが実装されています。  
  
3.  関数にオーバーライドがない場合は、プロパティ ウィンドウの右の列にあるセルをクリックし、\<add>*FuncName* として推奨される関数オーバーライドの名前を表示します。  
  
4.  推奨される名前をクリックして、関数のスタブ コードを追加します。  
  
5.  オーバーライド関数を編集するには、クラス ビューで関数の名前をダブルクリックし、ソース ウィンドウでコードを編集します。  
  
 オーバーライドを削除するには、右の列のオーバーライド関数名をクリックして、\<delete>*FuncName* を選択します。 関数のコードがコメントアウトされます。  
  
## <a name="see-also"></a>参照  
 [コード ウィザードを使用した機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [クラスの追加](../ide/adding-a-class-visual-cpp.md)   
 [メンバー関数の追加](../ide/adding-a-member-function-visual-cpp.md)   
 [メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md)   
 [MFC メッセージ ハンドラー](../mfc/reference/adding-an-mfc-message-handler.md)   
 [クラス各部へのジャンプ](../ide/navigating-the-class-structure-visual-cpp.md)