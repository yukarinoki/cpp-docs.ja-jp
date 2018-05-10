---
title: プログレス コントロールのスタイル |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- PBS_SMOOTH style
- progress controls [MFC], styles
- PBS_VERTICAL style
- CProgressCtrl class [MFC], styles
ms.assetid: 39eb8081-bc20-4552-91b9-e7cdd1b7d8ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c1044c82c2864d71047e4fe3c7461d03a17d9d3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="styles-for-the-progress-control"></a>プログレス コントロールのスタイル
プログレス コントロールを最初に作成する場合 ([CProgressCtrl::Create](../mfc/reference/cprogressctrl-class.md#create))、使用、`dwStyle`パラメーターを進行状況コントロールの目的のウィンドウ スタイルを指定します。 次の一覧では、適用できるウィンドウ スタイルについて説明します。 コントロールには、ここに一覧にない任意のウィンドウ スタイルが無視されます。 常に ダイアログ ボックスの親の通常の子ウィンドウとして、コントロールを作成します。  
  
|ウィンドウ スタイル|効果|  
|------------------|------------|  
|`WS_BORDER`|ウィンドウの周囲に罫線を作成します。|  
|**WS_CHILD**|子ウィンドウを作成します (に常に使用する必要があります`CProgressCtrl`)。|  
|**WS_CLIPCHILDREN**|親ウィンドウ内に描画するときに子ウィンドウにより占有される領域を除外します。 親ウィンドウを作成するときに使用します。|  
|**WS_CLIPSIBLINGS**|相対的な子ウィンドウをクリップします。|  
|**WS_DISABLED**|最初に無効になっているウィンドウを作成します。|  
|**WS_VISIBLE**|最初に表示されているウィンドウを作成します。|  
|**WS_TABSTOP**|ユーザーに移動して、TAB キーを押したときに、コントロールがフォーカスを受け取ることができますを指定します。|  
  
 さらに、進行状況コントロールのみに適用される 2 つのスタイルを指定できます`PBS_VERTICAL`と`PBS_SMOOTH`です。  
  
 使用して`PBS_VERTICAL`コントロールを水平方向にではなく縦向きにします。 使用して`PBS_SMOOTH`にコントロールを段階的に入力される小さなで区切られた四角形を表示するのではなく、完全にコントロールに入力します。  
  
 せず`PBS_SMOOTH`スタイル。  
  
 ![標準の進行状況バー スタイル](../mfc/media/vc4ruw1.gif "vc4ruw1")  
  
 `PBS_SMOOTH`と`PBS_VERTICAL`スタイル。  
  
 ![進行状況バーのスタイル、スムーズおよび垂直方向](../mfc/media/vc4ruw2.gif "vc4ruw2")  
  
 詳細については、次を参照してください。[ウィンドウ スタイル](../mfc/reference/styles-used-by-mfc.md#frame-window-styles-mfc)で、 *『 MFC リファレンス*です。  
  
## <a name="see-also"></a>関連項目  
 [CProgressCtrl の使い方](../mfc/using-cprogressctrl.md)

