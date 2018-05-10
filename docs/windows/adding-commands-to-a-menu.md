---
title: メニューにコマンドを追加する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.menu
dev_langs:
- C++
helpviewer_keywords:
- menu items, adding to menus
- menus, adding items
- commands, adding to menus
- commands
- menu items
ms.assetid: 1523a755-0ab5-42f8-9e98-bb9881564431
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e3564a808d39aa81ed3b45a1bc5812b285199e04
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="adding-commands-to-a-menu"></a>メニューへのコマンドの追加
### <a name="to-add-commands-to-a-menu"></a>メニューにコマンドを追加するには  
  
1.  [メニューを作成する](../windows/creating-a-menu.md)です。  
  
2.  メニュー名 ("ファイル" など) をクリックします。  
  
     各メニューが展開され、コマンド用の新しい項目ボックスが表示されます。 たとえば、[ファイル] メニューに [新規]、[開く]、[閉じる] の各コマンドを追加できます。  
  
3.  [新しい項目] ボックスに新しいメニュー コマンドの名前を入力します。  
  
    > [!NOTE]
    >  入力したテキストに表示されます両方メニュー エディターで、**キャプション**ボックスに、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。 新しいメニューのプロパティはこのどちらからでも編集できます。  
  
    > [!TIP]
    >  ユーザーがメニュー コマンドを選択できるようにするニーモニック キー (ホット キー) を定義することができます。 ニーモニックとして指定する文字の前にアンパサンド (&) を入力します。 この文字を入力することで、ユーザーはメニュー コマンドを選択できます。  
  
4.  プロパティ ウィンドウで、該当するメニュー コマンドのプロパティを選択します。 詳細については、「[メニュー コマンドのプロパティ](../windows/menu-command-properties.md)です。  
  
5.  **プロンプト**ボックスの [プロパティ] ウィンドウで、アプリケーションのステータス バーに表示するプロンプト文字列を入力します。  
  
     これにより、作成したメニュー コマンドと同じリソース識別子を持つエントリが文字列テーブル内に作成されます。  
  
    > [!NOTE]
    >  プロンプトがメニュー項目に適用できるだけ、**ポップアップ**プロパティ**True**です。 たとえば、トップレベルのメニュー項目にサブメニュー項目がある場合、プロンプトを適用できます。 プロンプトの目的は、ユーザーがメニュー項目をクリックしたときに発生する動作を示すことです。  
  
6.  キーを押して**ENTER**メニュー コマンドを完了します。  
  
     新しい項目ボックスが選択され、追加のメニュー コマンドを作成できるようになります。  
  

  
 **必要条件**  
  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [メニュー エディター](../windows/menu-editor.md)   
