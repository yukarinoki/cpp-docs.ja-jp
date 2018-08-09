---
title: メニューにコマンドの追加 |Microsoft Docs
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
ms.openlocfilehash: c0c744e920c71b74d9296e6961add704435658fe
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644730"
---
# <a name="adding-commands-to-a-menu"></a>メニューへのコマンドの追加
### <a name="to-add-commands-to-a-menu"></a>メニューにコマンドを追加するには  
  
1.  [メニューを作成する](../windows/creating-a-menu.md)します。  
  
2.  たとえば、メニューの名前をクリックします**ファイル**します。  
  
     各メニューが展開され、コマンド用の新しい項目ボックスが表示されます。 コマンドを追加するなど、**新規**、**オープン**と**閉じる**を**ファイル**メニュー。  
  
3.  [新しい項目] ボックスに新しいメニュー コマンドの名前を入力します。  
  
    > [!NOTE]
    >  入力したテキストは、 **メニュー** エディターと、 **プロパティ ウィンドウ** の [[キャプション]](/visualstudio/ide/reference/properties-window)ボックスの両方に表示されます。 新しいメニューのプロパティはこのどちらからでも編集できます。  
  
    > [!TIP]
    >  ユーザーがメニュー コマンドを選択できるようにするニーモニック キー (ホット キー) を定義することができます。 アンパサンドを入力 (`&`) ニーモニックとして指定する文字の前にします。 この文字を入力することで、ユーザーはメニュー コマンドを選択できます。  
  
4.  **プロパティ**ウィンドウで、メニュー コマンドを適用するプロパティを選択します。 詳細については、次を参照してください。[メニュー コマンドのプロパティ](../windows/menu-command-properties.md)します。  
  
5.  **プロンプト**ボックスに、**プロパティ**ウィンドウで、アプリケーションのステータス バーに表示するプロンプト文字列を入力します。  
  
     これにより、作成したメニュー コマンドと同じリソース識別子を持つエントリが文字列テーブル内に作成されます。  
  
    > [!NOTE]
    >  プロンプトがメニュー項目に適用できるだけ、**ポップアップ**プロパティの**True**します。 たとえば、トップレベルのメニュー項目にサブメニュー項目がある場合、プロンプトを適用できます。 目的を**プロンプト**をどうなるかを示すためには、ユーザーがメニュー項目をクリックした場合。  
  
6.  キーを押して**Enter**メニュー コマンドを完了します。  
  
     新しい項目ボックスが選択され、追加のメニュー コマンドを作成できるようになります。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [メニュー エディター](../windows/menu-editor.md)   