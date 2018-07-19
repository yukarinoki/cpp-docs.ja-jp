---
title: スピン ボタンのスタイル |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- styles [MFC], CSpinButtonCtrl
- CSpinButtonCtrl class [MFC], styles
- styles [MFC], spin button control
- spin button control, styles
ms.assetid: fb4a7f6f-9182-47be-bccf-0728fdc5332f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 223b7e0875a5382edf5f4d350c9343d117768c41
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953779"
---
# <a name="spin-button-styles"></a>スピン ボタンのスタイル
スピン ボタンの設定の多く ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)) スタイルによって制御されます。 使用して、次のスタイルを設定することができます、**プロパティ**ダイアログ エディターのウィンドウ。  
  
-   **印刷の向き**垂直または水平方向のいずれか。 矢印ボタンの方向を制御します。 UDS_HORZ スタイルに関連付けられました。  
  
-   **配置**結び付けられていない、左右のいずれか。 スピン ボタンの場所を制御します。 Left と Right は、関連ウィンドウの横にあるスピン ボタンを配置します。 スピン ボタンに対応する関連ウィンドウの幅を縮小します。 UDS_ALIGNLEFT と UDS_ALIGNRIGHT スタイルに関連付けられました。  
  
-   **Auto Buddy**スピン ボタンの連動ウィンドウとして Z オーダーで前のウィンドウを自動的に選択します。 ダイアログ テンプレートで、これは、スピン ボタンの前に、タブ オーダーのコントロールです。 UDS_AUTOBUDDY スタイルに関連付けられました。  
  
-   **設定 Buddy Integer**スピン コントロールをインクリメントおよび現在の位置の変更と連動ウィンドウのキャプションをデクリメントします。 UDS_SETBUDDYINT スタイルに関連付けられました。  
  
-   **Nothousands**桁は挿入されませんが連動ウィンドウのキャプションの値の区切り記号。 UDS_NOTHOUSANDS スタイルに関連付けられました。  
  
    > [!NOTE]
    >  ダイアログ データ エクス (チェンジ DDX) を使用して、アップダウン コントロールからの整数値を取得する場合は、このスタイルを設定します。 `DDX_Text` 埋め込みの桁区切り記号は受け入れられません。  
  
-   **ラップ**によって「ラップ」値がインクリメントまたはデクリメント コントロールの範囲外に位置します。 UDS_WRAP スタイルに関連付けられました。  
  
-   **方向キー**スピン ボタンの上方向キーおよび ↓ キーが押されたときに、位置を増減します。 UDS_ARROWKEYS スタイルに関連付けられました。  
  
## <a name="see-also"></a>関連項目  
 [CSpinButtonCtrl の使い方](../mfc/using-cspinbuttonctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

