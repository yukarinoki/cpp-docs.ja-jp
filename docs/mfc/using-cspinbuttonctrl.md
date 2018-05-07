---
title: CSpinButtonCtrl の使い方 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CSpinButtonCtrl
dev_langs:
- C++
helpviewer_keywords:
- up-down controls [MFC], spin button control
- up-down controls
- spin button control
- CSpinButtonCtrl class [MFC], using
ms.assetid: a91db36b-e11e-42ef-8e89-51915cc486d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 03b1e83977c1d75070e8878dfdcc53c7afca7a86
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="using-cspinbuttonctrl"></a>CSpinButtonCtrl の使い方
*スピン ボタン*コントロール (とも呼ばれる、*アップダウン*コントロール)、値を調整するユーザーがクリックして表示する矢印のペアを提供します。 この値と呼ばれる、*現在位置*です。 スピン ボタンの範囲内の位置が維持されます。 位置が最大に向かって移動、ユーザーは、上向きの矢印をクリックすると、最小に向かって、ユーザーは、下向きの矢印をクリックすると、位置が移動します。  
  
 スピン ボタン コントロールは、MFC では、 [CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)クラスです。  
  
> [!NOTE]
>  既定では、スピン ボタンの範囲が、ゼロ (0) に設定した最大値、最小値が 100 に設定します。 最大値は最小値よりも小さいため、上向きの矢印をクリックすると、位置が減少になり、下矢印をクリックすると、できます。 使用して[上限値と下限](../mfc/reference/cspinbuttonctrl-class.md#setrange)をこれらの値を調整します。  
  
 通常、現在の位置は、横にあるコントロールに表示されます。 コンパニオン コントロールと呼ばれる、*関連ウィンドウ*します。 スピン ボタン コントロールの図解は、次を参照してください。[アップダウン コントロールに関する](http://msdn.microsoft.com/library/windows/desktop/bb759889)Windows SDK に含まれています。  
  
 Visual Studio で、スピン コントロールとを編集コントロールの連動ウィンドウを作成するには、最初にダイアログ ボックスまたはウィンドウで、エディット コントロールをドラッグしをスピン コントロールをドラッグします。 スピン コントロールを選択し、設定、 **Auto Buddy**と**Buddy Integer の設定**プロパティ**True**です。 設定も、**配置**プロパティです。**右揃え**が一般的です。 エディット コントロールは、これらの設定で、タブ オーダーのエディット コントロールで直接前置ため連動ウィンドウとして設定されます。 編集コントロールは、整数を表示し、エディット コントロールの右側に、スピン コントロールが埋め込まれたします。 必要に応じてを使用して、スピン コントロールの有効範囲を設定することができます、[上限値と下限](../mfc/reference/cspinbuttonctrl-class.md#setrange)メソッドです。 データを直接交換するため、スピン コントロールと連動ウィンドウ間の通信には、イベント ハンドラーは必要ありません。 他の何らかの目的をスピン コントロールを使用する場合など、ウィンドウやダイアログ ボックスのシーケンスを改ページし、ハンドラーを追加、`UDN_DELTAPOS`メッセージし、カスタム アクションを実行します。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [スピン ボタンのスタイル](../mfc/spin-button-styles.md)  
  
-   [スピン ボタンのメンバー関数](../mfc/spin-button-member-functions.md)  
  
## <a name="see-also"></a>関連項目  
 [コントロール](../mfc/controls-mfc.md)

