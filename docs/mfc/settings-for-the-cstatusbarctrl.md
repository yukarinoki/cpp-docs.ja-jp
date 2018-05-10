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
ms.openlocfilehash: 1eea701c33001ffa3585c2d5847f3056454b7850
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="settings-for-the-cstatusbarctrl"></a>CStatusBarCtrl の設定値
既定の位置、 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)ステータス ウィンドウが、親ウィンドウの下部では、指定することが、`CCS_TOP`スタイルを親ウィンドウのクライアント領域の上部に表示します。  
  
 指定することができます、 **SBARS_SIZEGRIP**を含めるの右端にあるサイズ変更グリップのスタイル、`CStatusBarCtrl`ステータス ウィンドウです。 サイズ変更グリップがサイズ変更境界線; に似ています。これは、ユーザーをクリックして親ウィンドウのサイズにドラッグされる四角形の領域です。  
  
> [!NOTE]
>  結合する場合、`CCS_TOP`と**SBARS_SIZEGRIP**スタイル、サイズ変更グリップを結果として得られるが機能していない場合でも、システムは、ステータス ウィンドウに描画します。  
  
 ステータス ウィンドウのウィンドウ プロシージャは、初期サイズとコントロール ウィンドウの位置に自動的に設定します。 幅は、親ウィンドウのクライアント領域のと同じです。 高さは、ステータス ウィンドウのデバイス コンテキストに現在選択されているフォントのメトリックとウィンドウの境界線の幅に基づいています。  
  
 ウィンドウ プロシージャは、ステータス ウィンドウのサイズを自動的に調整を受け取るたびに、`WM_SIZE`メッセージ。 通常、親ウィンドウのサイズが変更されたとき、親の送信、`WM_SIZE`ステータス ウィンドウにメッセージ。  
  
 ステータス ウィンドウの描画領域の高さの最小値を設定するには呼び出すことによって[SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight)ピクセルの高さの最小値を指定します。 描画領域では、ウィンドウの境界線は含まれません。  
  
 呼び出して、ステータス ウィンドウの境界線の幅を取得する[GetBorders](../mfc/reference/cstatusbarctrl-class.md#getborders)です。 このメンバー関数には、水平方向の境界線、垂直方向の境界線および四角形の間の境界線の幅を受け取る 3 要素の配列へのポインターが含まれています。  
  
## <a name="see-also"></a>関連項目  
 [CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

