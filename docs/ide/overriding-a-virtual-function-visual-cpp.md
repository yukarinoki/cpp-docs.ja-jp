---
description: '詳細情報: 仮想関数をオーバーライドする'
title: 仮想関数をオーバーライドする
ms.date: 11/12/2018
f1_keywords:
- vc.codewiz.virtualfunc.override
helpviewer_keywords:
- virtual functions, overriding
- base classes, overriding virtual functions defined in
- Properties window, overriding virtual functions in
ms.assetid: 2d8c76f2-7a6b-4c9c-8de5-4282ce7755b6
ms.openlocfilehash: d4c800006d5227ed5397c17284c03968a24a3964
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335916"
---
# <a name="override-a-virtual-function"></a>仮想関数をオーバーライドする

Visual Studio の[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)では、基本クラスで定義されている仮想関数をオーバーライドすることができます。

**プロパティ ウィンドウで仮想関数をオーバーライドするには:**

1. クラス ビューで、クラスを選択します。

1. プロパティ ウィンドウで、**[オーバーライド]** ボタンを選択します。

   > [!NOTE]
   > **[オーバーライド]** ボタンは、クラス ビューでクラス名を選択したとき、またはソース ウィンドウ内を選択したときに使用できます。

   左の列には仮想関数が一覧表示されます。 右の列にも仮想関数の名前が表示される場合は、既にオーバーライドが実装されています。

1. 関数にオーバーライドがない場合は、プロパティ ウィンドウの右の列にあるセルを選択し、\<add>*FuncName* として推奨される関数オーバーライドの名前を表示します。

1. 推奨される名前を選択して、関数のスタブ コードを追加します。

1. オーバーライド関数を編集するには、クラス ビューで関数の名前をダブルクリックし、ソース ウィンドウでコードを編集します。

オーバーライドを削除するには、右の列のオーバーライド関数名を選択して、\<delete>*FuncName* を選択します。 関数のコードがコメントアウトされます。
