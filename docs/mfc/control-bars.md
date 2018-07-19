---
title: コントロール バー |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- command bars [MFC], types of
- toolbars [MFC], control bars
- control bars [MFC]
- MFC, control bars
- control bars [MFC], types of
- CDialogBar class [MFC], control bars
- status bars [MFC], control bars
- CControlBar class [MFC], MFC control bars
- dialog bars [MFC], control bars
- CToolBar class [MFC], control bars
- CStatusBar class [MFC], control bars
ms.assetid: 31831910-3d23-4d70-9e71-03cc02f01ec4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 179e959ce4d6a516f51576712e50408ef41d5c7e
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931792"
---
# <a name="control-bars"></a>コントロール バー
「コントロール バー」は、ツールバー、ステータス バー、およびダイアログ バーの [全般] の名前です。 MFC クラス`CToolBar`、 `CStatusBar`、 `CDialogBar`、 `COleResizeBar`、および`CReBar`クラスから派生[CControlBar](../mfc/reference/ccontrolbar-class.md)、一般的な機能を実装します。  
  
 コントロール バーは、コントロールをユーザーできますオプションを選択、コマンドを実行またはプログラム情報の取得の行を表示するウィンドウです。 コントロール バーの種類には、ツールバー、ダイアログ バー、およびステータス バーが含まれます。  
  
-   クラスで、ツールバー [CToolBar](../mfc/reference/ctoolbar-class.md)  
  
-   クラスのステータス バー、 [CStatusBar](../mfc/reference/cstatusbar-class.md)  
  
-   クラスでのダイアログ バー [CDialogBar](../mfc/reference/cdialogbar-class.md)  
  
-   クラスでの rebars [CReBar](../mfc/reference/crebar-class.md)  
  
> [!IMPORTANT]
>  MFC バージョン 4.0、ツールバー、ステータス バー、およびツールの時点でヒントを実装に実装されているシステム機能を使用して、 *comctl32.dll* MFC 固有の以前の実装ではなくです。 Mfc バージョン 6.0 では、 `CReBar`、comctl32.dll 機能をラップするも追加されました。  
  
 簡単な概要については、コントロール バーの種類に従ってください。 詳細については、以下のリンクを参照してください。  
  
## <a name="control-bars"></a>コントロール バー  
 コントロール バーは、クイック、ワンステップ コマンド操作を提供することにより、プログラムの使いやすさを大幅に向上します。 クラス`CControlBar`すべてのツールバー、ステータス バー、およびダイアログ バーの一般的な機能を提供します。 `CControlBar` 親フレーム ウィンドウ内のコントロール バーの位置の機能を提供します。 コントロール バーは、親フレーム ウィンドウの子ウィンドウでは通常、ためにはクライアント ビューまたはフレーム ウィンドウの MDI クライアントへの「兄弟」です。 コントロール バー オブジェクトは、それ自体を配置、親ウィンドウのクライアントの四角形に関する情報を使用します。 クライアントの表示または MDI クライアント ウィンドウの残りの部分、クライアント ウィンドウを親の残りのクライアント ウィンドウ領域を変更します。  
  
> [!NOTE]
>  コントロール バーのボタンを持っていない場合、**コマンド**または**UPDATE_COMMAND_UI**ハンドラー、フレームワークが自動的に、ボタンを無効にします。  
  
## <a name="toolbars"></a>ツールバー  
 ツールバーは、コマンドを実行するビットマップのボタンの行を表示するコントロール バーです。 ツール バー ボタンを押すとは、メニュー項目を選択することと同じこれは、そのメニュー項目は、ツール バー ボタンと同じ ID を持つ場合、メニュー項目にマップされている同じハンドラーを呼び出します。 ボタンは、プッシュ ボタン、オプション ボタンまたはチェック ボックスとして表示して機能を構成できます。 ツールバーは通常、フレーム ウィンドウの上部に配置が、MFC ツールバーできます「ドッキング」の親ウィンドウまたは独自のミニフレーム ウィンドウとしてフローティングの任意の辺にします。 ツールバーも「をフローティングできる」とそのサイズを変更し、マウスでドラッグします。 ツールバーは、ユーザーは、ツールバーのボタンにマウスを移動にも、ツール ヒントに表示できます。 ツール ヒントは、ボタンの用途を簡単に説明する小さなポップアップ ウィンドウです。  
  
> [!NOTE]
>  MFC バージョン 4.0 の時点でクラス[CToolBar](../mfc/reference/ctoolbar-class.md) Windows ツール バー コモン コントロールを使用します。 A`CToolBar`が含まれています、 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)です。 ただし、古いツールバーはサポートもします。 記事を参照して[ツールバー](../mfc/mfc-toolbar-implementation.md)です。  
  
## <a name="status-bars"></a>ステータス バー  
 ステータス バーは、テキスト出力ペイン、または「インジケーター」を含むコントロール バー 出力ウィンドウは、状態インジケーター、およびメッセージ行としてよく使用されます。 メッセージの行の例には、選択したメニューまたは MFC アプリケーション ウィザードによって作成された既定のステータス バーの一番左のウィンドウで、ツール バー コマンドを簡単に説明するコマンドライン ヘルプ メッセージにはが含まれます。 インジケーターの状態の例には、SCROLL LOCK、NUM LOCK、およびその他のキーが含まれます。 ステータス バーは、通常、フレーム ウィンドウの下部に配置されます。 クラスを参照して[CStatusBar](../mfc/reference/cstatusbar-class.md)とクラス[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)です。  
  
## <a name="dialog-bars"></a>ダイアログ バー  
 ダイアログ バーは、モードレス ダイアログ ボックスの機能をダイアログ テンプレート リソースに基づいて、コントロール バーです。 ダイアログ バーは、Windows を含めることができるカスタム、または ActiveX コントロール。 ダイアログ ボックスと同様に、ユーザーは、コントロール間タブことができます。 ダイアログ バーを上、下、左、またはフレーム ウィンドウの右側に配置できるし、独自のフレーム ウィンドウにフロートすることもできます。 クラスを参照して[CDialogBar](../mfc/reference/cdialogbar-class.md)です。  
  
## <a name="rebars"></a>Rebars  
 A [rebar](../mfc/using-crebarctrl.md)が rebar コントロールのドッキング、レイアウト、state、および持続性の情報を提供するコントロール バーです。 Rebar オブジェクトは、子ウィンドウ、通常その他のコントロール、編集ボックス、ツールバー、リスト ボックスなどのさまざまなを含めることができます。 Rebar オブジェクトは、指定したビットマップをその子ウィンドウを表示できます。 自動または手動でサイズを変更できるをクリックするかのグリッパー バーをドラッグします。 クラスを参照して[CReBar](../mfc/reference/crebar-class.md)です。  
  
## <a name="see-also"></a>関連項目  
 [ユーザー インターフェイス要素](../mfc/user-interface-elements-mfc.md)
