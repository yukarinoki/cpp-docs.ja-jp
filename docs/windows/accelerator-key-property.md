---
title: アクセラレータ キー プロパティ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Key property
ms.assetid: d1570cd9-b414-4cd6-96bd-47c38281eaca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e4fc56384d666026f4cc7e21f9d8af9347046fd1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857208"
---
# <a name="accelerator-key-property"></a>アクセラレータの [キー] プロパティ
アクセラレータ テーブル内のキー プロパティに有効なエントリを次に示します。  
  
-   0 から 10 進数形式で 255 までの整数。 値は、値が ASCII または ANSI として次のように扱われるかどうかを決定します。  
  
    -   1 桁の数字は、常に、ASCII または ANSI の値ではなく、対応するキーとして解釈されます。  
  
    -   1 ~ 26、0 が付く場合の値として解釈されます ^ A ~ ^ Z で、CTRL キーを押したままの状態と押されたときに、アルファベットの文字の ASCII 値を表します。  
  
    -   27 ~ 32 の値は常に、3 桁の 10 進値 027 ~ 032 として解釈されます。  
  
    -   033 ~ 255 の値の 0 の前に付けたまたはいない ANSI 値として解釈されるかどうかです。  
  
-   1 つのキーボード文字。 大文字の A ~ Z、または 0 ~ 9 の数字は、ASCII または仮想キー値のいずれかを指定できます。その他の文字には ASCII のみです。  
  
-   A ~ Z の範囲内の 1 つのキーボード文字 (大文字のみ)、キャレット (^) の前に (たとえば、^ C)。 これにより、CTRL キーを押したままの状態が押されたときに、キーの ASCII 値が入力されます。  
  
    > [!NOTE]
    >  ASCII 値を入力するときに修飾子プロパティのオプションは限定されます。 使用するため利用可能な唯一のコントロール キーは、ALT キーです。  
  
-   有効な仮想キーの識別子。 アクセラレータ テーブルでドロップダウンのキーのボックスには、標準の仮想キー識別子の一覧が含まれています。  
  
    > [!TIP]
    >  アクセラレータ キーを定義する別の方法は、エントリまたはアクセラレータ テーブル内の複数のエントリを右クリックしを選択する**キー タイピング登録**ショートカット メニューからキーまたはキーの組み合わせのいずれか、キーボードのキーを押します。 **キー タイピング登録**コマンドはまた、**編集**メニュー。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [アクセラレータのプロパティの設定](../windows/setting-accelerator-properties.md)   
 [アクセラレータ テーブルでの編集](../windows/editing-in-an-accelerator-table.md)   
 [アクセラレータ エディター](../windows/accelerator-editor.md)