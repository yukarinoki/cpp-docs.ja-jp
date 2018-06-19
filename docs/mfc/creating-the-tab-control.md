---
title: タブ コントロールの作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- TCS_EX_REGISTERDROP
- TCS_EX_FLATSEPARATORS
dev_langs:
- C++
helpviewer_keywords:
- TCS_EX_REGISTERDROP extended style [MFC]
- tab controls [MFC], creating
- CTabCtrl class [MFC], creating
- TCS_EX_FLATSEPARATORS extended style
ms.assetid: 3a9c2d64-f5f4-41ea-84ab-fceb73c3dbdc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3945d441130d723bbda3d137f2adae637d56c2b6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344092"
---
# <a name="creating-the-tab-control"></a>タブ コントロールの作成
タブ コントロールの作成方法は、ダイアログ ボックスで、コントロールの使用か以外のウィンドウで作成するかによって異なります。  
  
### <a name="to-use-ctabctrl-directly-in-a-dialog-box"></a>ダイアログ ボックスで直接 CTabCtrl を使用するには  
  
1.  ダイアログ エディターでダイアログ テンプレート リソース タブのコントロールを追加します。 そのコントロールの ID を指定します  
  
2.  使用して、[メンバー変数の追加ウィザード](../ide/adding-a-member-variable-visual-cpp.md)型のメンバー変数を追加する[CTabCtrl](../mfc/reference/ctabctrl-class.md)コントロールのプロパティにします。 このメンバーを使用するを呼び出すと`CTabCtrl`メンバー関数。  
  
3.  タブ コントロール通知メッセージを処理する必要がありますダイアログ クラスのハンドラー関数にマップします。 詳細については、次を参照してください。[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md)です。  
  
4.  [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)のスタイルを設定、`CTabCtrl`です。  
  
### <a name="to-use-ctabctrl-in-a-nondialog-window"></a>以外のウィンドウで CTabCtrl を使用するには  
  
1.  ビューまたはウィンドウのクラスでは、コントロールを定義します。  
  
2.  コントロールの呼び出します[作成](../mfc/reference/ctabctrl-class.md#create)メンバー関数は、可能性のあるで[フィルターと並べ替え順序](../mfc/reference/cview-class.md#oninitialupdate)、親ウィンドウの可能性がありますの早期[OnCreate](../mfc/reference/cwnd-class.md#oncreate)ハンドラー関数 (ユーザー場合サブクラス化コントロール)。 コントロールのスタイルを設定します。  
  
 後に、`CTabCtrl`オブジェクトが作成された、設定または、次の拡張スタイルをオフにすることができます。  
  
-   **TCS_EX_FLATSEPARATORS**タブ コントロールは、タブ項目間の区切り記号を描画します。 これは、拡張スタイルのみに影響を持つコントロールのタブ、 **TCS_BUTTONS**と**TCS_FLATBUTTONS**スタイル。 既定を持つタブ コントロールの作成、 **TCS_FLATBUTTONS**スタイルがこのスタイルの拡張を設定します。  
  
-   **TCS_EX_REGISTERDROP**タブ コントロールが生成**TCN_GETOBJECT**ドロップ ターゲットを要求する通知メッセージ オブジェクトのオブジェクトがコントロールのタブ項目をドラッグするとします。  
  
    > [!NOTE]
    >  受信する、 **TCN_GETOBJECT** 、通知への呼び出しと OLE ライブラリを初期化する必要があります[AfxOleInit](../mfc/reference/ole-initialization.md#afxoleinit)です。  
  
 これらのスタイルを取得し、設定、コントロールが作成された後、それぞれの呼び出しを[GetExtendedStyle](../mfc/reference/ctabctrl-class.md#getextendedstyle)と[拡張](../mfc/reference/ctabctrl-class.md#setextendedstyle)メンバー関数。  
  
 たとえば、設定、 **TCS_EX_FLATSEPARATORS**と次のコード行のスタイル。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#33](../mfc/codesnippet/cpp/creating-the-tab-control_1.cpp)]  
  
 クリア、 **TCS_EX_FLATSEPARATORS**からスタイルを設定、`CTabCtrl`次のコード行を持つオブジェクト。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#34](../mfc/codesnippet/cpp/creating-the-tab-control_2.cpp)]  
  
 ボタンの間に表示される区切り記号が削除されます、`CTabCtrl`オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [CTabCtrl の使い方](../mfc/using-ctabctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

