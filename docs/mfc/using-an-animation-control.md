---
title: アニメーション コントロールの使い方 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [MFC], animation
- CAnimateCtrl class [MFC], animation controls
- animation controls [MFC]
ms.assetid: a009a464-e12d-4112-bf52-04a09b28dd88
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ecde11ddb55992032b2a8b052e2897a384293bc0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382555"
---
# <a name="using-an-animation-control"></a>アニメーション コントロールの使い方
アニメーション コントロールの一般的な使用方法は、次のパターンを次に示します。  
  
-   コントロールが作成されます。 コントロールがダイアログ ボックスのテンプレートで指定されている場合、ダイアログ ボックスの作成時に作成は自動です。 (必要、 [CAnimateCtrl](../mfc/reference/canimatectrl-class.md)アニメーション コントロールに対応するダイアログ クラスのメンバーです)。また、使用することができます、[作成](../mfc/reference/canimatectrl-class.md#create)メンバー関数を任意のウィンドウの子ウィンドウとして、コントロールを作成します。  
  
-   アニメーション コントロールに呼び出すことによって、AVI クリップを読み込む、[開く](../mfc/reference/canimatectrl-class.md#open)メンバー関数。 アニメーション コントロールがダイアログ ボックス内にある場合は、これを行うことをおすすめはダイアログ クラスの[OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)関数。  
  
-   呼び出して、クリップの再生、[再生](../mfc/reference/canimatectrl-class.md#play)メンバー関数。 アニメーション コントロールがダイアログ ボックス内にある場合は、これを行うことをおすすめはダイアログ クラスの**OnInitDialog**関数。 呼び出す**再生**アニメーション コントロールがある場合は必要ありません、`ACS_AUTOPLAY`セットのスタイルを設定します。  
  
-   クリップの部分を表示またはフレームごとの使用を再生する場合、`Seek`メンバー関数。 停止するには、クリップの再生を使用して、`Stop`メンバー関数。  
  
-   コントロールの破棄をすぐに行わない場合、クリップをメモリから削除を呼び出して、**閉じる**メンバー関数。  
  
-   アニメーション コントロールがダイアログ ボックスでは、場合、および`CAnimateCtrl`オブジェクトは自動的に破棄されます。 かどうか、する必要はありません、両方のコントロールをことを確認して、`CAnimateCtrl`オブジェクトが破棄されました。 コントロールを自動的に破棄するには、AVI クリップが閉じられます。  
  
## <a name="see-also"></a>関連項目  
 [CAnimateCtrl の使い方](../mfc/using-canimatectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

