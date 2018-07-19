---
title: CStatusBarCtrl の設定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- status bar controls [MFC], settings
- CStatusBarCtrl class [MFC], settings
ms.assetid: adeba0c3-17f3-435c-b140-a57845e9ce49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1dde1f005e53aff7ebe505d1ce619bf5c94410f8
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36955457"
---
# <a name="settings-for-the-cstatusbarctrl"></a>CStatusBarCtrl の設定値
既定の位置、 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)親ウィンドウの下部では、ステータス ウィンドウが、親ウィンドウのクライアント領域の上部に表示させる CCS_TOP スタイルを指定することができます。  
  
 右端にあるサイズ変更グリップを含める SBARS_SIZEGRIP スタイルを指定することができます、`CStatusBarCtrl`ステータス ウィンドウです。 サイズ変更グリップがサイズ変更境界線; に似ています。これは、ユーザーをクリックして親ウィンドウのサイズにドラッグされる四角形の領域です。  
  
> [!NOTE]
>  CCS_TOP と SBARS_SIZEGRIP のスタイルを結合する場合、結果のサイズ変更グリップは、システムは、ステータス ウィンドウに描画にもかかわらずと機能しません。  
  
 ステータス ウィンドウのウィンドウ プロシージャは、初期サイズとコントロール ウィンドウの位置に自動的に設定します。 幅は、親ウィンドウのクライアント領域のと同じです。 高さは、ステータス ウィンドウのデバイス コンテキストに現在選択されているフォントのメトリックとウィンドウの境界線の幅に基づいています。  
  
 ウィンドウ プロシージャは、WM_SIZE メッセージを受信するたびに、ステータス ウィンドウのサイズを自動的に調整されます。 通常、親ウィンドウのサイズが変更されたときに、親は、ステータス ウィンドウに WM_SIZE メッセージを送信します。  
  
 ステータス ウィンドウの描画領域の高さの最小値を設定するには呼び出すことによって[SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight)ピクセルの高さの最小値を指定します。 描画領域では、ウィンドウの境界線は含まれません。  
  
 呼び出して、ステータス ウィンドウの境界線の幅を取得する[GetBorders](../mfc/reference/cstatusbarctrl-class.md#getborders)です。 このメンバー関数には、水平方向の境界線、垂直方向の境界線および四角形の間の境界線の幅を受け取る 3 要素の配列へのポインターが含まれています。  
  
## <a name="see-also"></a>関連項目  
 [CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

