---
title: Cspinbuttonctrl の使い方 |Microsoft Docs
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
ms.openlocfilehash: 3768cda94eb0adda8562c46124be8e9b2d4a2501
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215093"
---
# <a name="using-cspinbuttonctrl"></a>CSpinButtonCtrl の使い方
*スピン ボタン*コントロール (とも呼ばれる、*アップダウン*コントロール)、値を調整するユーザーがクリックする矢印のペアを提供します。 この値と呼ばれる、*現在位置*します。 スピン ボタンの範囲内に位置が維持されます。 位置が最大に向かって移動ユーザーは、上向きの矢印をクリックすると、最小値に、ユーザーは、下矢印をクリックすると、位置が移動します。  
  
 スピン ボタン コントロールは、MFC では、 [CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)クラス。  
  
> [!NOTE]
>  既定では、スピン ボタンの範囲が、ゼロ (0) に設定した最大値、最小値が 100 に設定します。 最大値は最小値より小さいため、上向きの矢印をクリックすると、位置が減少し、下矢印をクリックすると拡大します。 使用[上限値と下限](../mfc/reference/cspinbuttonctrl-class.md#setrange)をこれらの値を調整します。  
  
 通常、現在の位置は、コントロールに表示されます。 付属のコントロールと呼ばれる、*連動ウィンドウ*します。 スピン ボタン コントロールの図解は、次を参照してください。[アップ ダウン コントロールに関する](/windows/desktop/Controls/up-down-controls)Windows SDK に含まれています。  
  
 Visual Studio で、スピン コントロールとを編集コントロールの連動ウィンドウを作成するには、最初にダイアログ ボックスまたはウィンドウで、エディット コントロールをドラッグしをスピン コントロールをドラッグします。 スピン コントロールを選択し、設定、 **Auto Buddy**と**設定 Buddy Integer**プロパティを**True**します。 設定しても、**配置**プロパティです。**右揃え**が最も一般的です。 これらの設定で、編集コントロールは、タブ オーダー内で直接編集コントロールの前にあるため連動ウィンドウとして設定されます。 エディット コントロールは、整数を表示し、スピン コントロールが編集コントロールの右側に埋め込まれました。 必要に応じてを使用して、スピン コントロールの有効な範囲を設定することができます、[上限値と下限](../mfc/reference/cspinbuttonctrl-class.md#setrange)メソッド。 データを直接交換するため、スピン コントロールと連動ウィンドウ間の通信には、イベント ハンドラーは必要ありません。 別の目的をスピン コントロールを使用する場合など、一連のウィンドウまたはダイアログ ボックスでは、改ページする UDN_DELTAPOS メッセージのハンドラーを追加し、しアクションを実行、カスタムがあります。  
  
## <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います  
  
-   [スピン ボタンのスタイル](../mfc/spin-button-styles.md)  
  
-   [スピン ボタンのメンバー関数](../mfc/spin-button-member-functions.md)  
  
## <a name="see-also"></a>関連項目  
 [コントロール](../mfc/controls-mfc.md)

