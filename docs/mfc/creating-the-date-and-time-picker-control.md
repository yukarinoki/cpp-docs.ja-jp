---
title: コントロールの日付と時刻の選択を作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DateTimePicker control [MFC], creating
- CDateTimeCtrl class [MFC], creating
ms.assetid: 764ec2fb-98cd-478b-a5f2-d63f0bb12279
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6ce7c987bf1284d0287cd0206572209d7ae2d0b7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="creating-the-date-and-time-picker-control"></a>日時指定コントロールの作成
日付と時刻の選択コントロールを作成する方法は、ダイアログ ボックスで、コントロールの使用か以外のウィンドウで作成するかによって異なります。  
  
### <a name="to-use-cdatetimectrl-directly-in-a-dialog-box"></a>ダイアログ ボックスで直接 CDateTimeCtrl を使用するには  
  
1.  ダイアログ エディターでダイアログ テンプレート リソースに日付と時刻の選択コントロールを追加します。 そのコントロールの ID を指定します  
  
2.  日付と時刻の選択コントロールのプロパティ ダイアログ ボックスを使用するように、必要に応じてのスタイルを指定します。  
  
3.  使用して、[メンバー変数の追加ウィザード](../ide/adding-a-member-variable-visual-cpp.md)型のメンバー変数を追加する[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)コントロールのプロパティにします。 このメンバーを使用するを呼び出すと`CDateTimeCtrl`メンバー関数。  
  
4.  [プロパティ] ウィンドウを使用して、日時指定コントロールのダイアログ クラスのハンドラー関数にマップする[通知](../mfc/processing-notification-messages-in-date-and-time-picker-controls.md)メッセージを処理する必要があります (を参照してください[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md))。  
  
5.  [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)、その他のスタイルを設定、`CDateTimeCtrl`オブジェクト。  
  
### <a name="to-use-cdatetimectrl-in-a-nondialog-window"></a>以外のウィンドウで CDateTimeCtrl を使用するには  
  
1.  ビューまたはウィンドウのクラス内のコントロールを宣言します。  
  
2.  コントロールの呼び出します[作成](../mfc/reference/ctabctrl-class.md#create)メンバー関数は、可能性のあるで[フィルターと並べ替え順序](../mfc/reference/cview-class.md#oninitialupdate)、親ウィンドウの可能性がありますの早期[OnCreate](../mfc/reference/cwnd-class.md#oncreate)ハンドラー関数 (ユーザー場合サブクラス化コントロール)。 コントロールのスタイルを設定します。  
  
## <a name="see-also"></a>関連項目  
 [CDateTimeCtrl の使い方](../mfc/using-cdatetimectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

