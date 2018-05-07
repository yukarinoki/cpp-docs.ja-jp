---
title: '例: メニュー コマンドによるダイアログ ボックスの表示 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], examples
- MFC dialog boxes [MFC], displaying
- modeless dialog boxes [MFC], displaying
- dialog boxes [MFC], MFC
- modal dialog boxes [MFC], displaying
- examples [MFC], dialog boxes
- menu items [MFC], examples
ms.assetid: e8692549-acd7-478f-9c5e-ba310ce8cccd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 20d355215388861a7bc2586c2c253cd551124809
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="example-displaying-a-dialog-box-via-a-menu-command"></a>例 : メニュー コマンドによるダイアログ ボックスの表示
このトピックには、プロシージャが含まれています。  
  
-   メニュー コマンドを使って、モーダル ダイアログ ボックスを表示します。  
  
-   メニュー コマンドを使ってモードレス ダイアログ ボックスを表示します。  
  
 両方のサンプル手順は、MFC アプリケーションとを作成するアプリケーションでは機能、 [MFC アプリケーション ウィザード](../mfc/reference/mfc-application-wizard.md)です。  
  
 手順は、次の名前と値を使用します。  
  
|アイテム|名前または値|  
|----------|-------------------|  
|アプリケーション|DisplayDialog|  
|メニュー コマンド|テスト メニューのコマンドを表示します。コマンド ID ID_VIEW_TEST を =|  
|ダイアログ ボックス|テスト ダイアログ ボックスです。クラス CTestDialog; を =ヘッダー ファイル TestDialog.h; を =変数 testdlg、ptestdlg を =|  
|コマンド ハンドラー|OnViewTest|  
  
### <a name="to-display-a-modal-dialog-box"></a>モーダル ダイアログ ボックスを表示するには  
  
1.  メニュー コマンドを作成します。参照してください[を作成するメニューまたはメニュー項目](../windows/creating-a-menu.md)です。  
  
2.  ダイアログ ボックスを作成します。参照してください[ダイアログ エディターを起動](../windows/creating-a-new-dialog-box.md)です。  
  
3.  ダイアログ ボックスのクラスを追加します。 参照してください[クラスの追加](../ide/adding-a-class-visual-cpp.md)詳細についてはします。  
  
4.  **クラス ビュー**、ドキュメント クラス (CDisplayDialogDoc) を選択します。 **[プロパティ]** ウィンドウで、 **[イベント]** ボタンをクリックします。 左側のウィンドウで、メニュー コマンド (ID_VIEW_TEST) の ID をダブルクリックして、**プロパティ**ウィンドウと選択**コマンド**です。 右側のウィンドウで、下矢印をクリックし、選択**\<追加 > OnViewTest**です。  
  
     MDI アプリケーションのメインフレームにメニュー コマンドを追加する場合は、代わりに、アプリケーション クラス (CDisplayDialogApp) を選択します。  
  
5.  ステートメント CDisplayDialogDoc.cpp (または CDisplayDialogApp.cpp) を次を追加、既存の include ステートメントの後。  
  
     [!code-cpp[NVC_MFCControlLadenDialog#42](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_1.cpp)]  
  
6.  次のコードを追加`OnViewTest`関数を実装します。  
  
     [!code-cpp[NVC_MFCControlLadenDialog#43](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_2.cpp)]  
  
### <a name="to-display-a-modeless-dialog-box"></a>モードレス ダイアログ ボックスを表示するには  
  
1.  手順 4. で、ビュー クラス (CDisplayDialogView) を選択する点を除いて、モーダル ダイアログ ボックスを表示する最初の 4 つの手順を実行します。  
  
2.  DisplayDialogView.h を編集します。  
  
    -   最初のクラス宣言の前のダイアログ ボックス クラスを宣言します。  
  
         [!code-cpp[NVC_MFCControlLadenDialog#44](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_3.h)]  
  
    -   属性のパブリック セクションの後に、ダイアログ ボックスへのポインターを宣言します。  
  
         [!code-cpp[NVC_MFCControlLadenDialog#45](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_4.h)]  
  
3.  DisplayDialogView.cpp を編集します。  
  
    -   次のステートメントを含める後、既存の include ステートメントを追加します。  
  
         [!code-cpp[NVC_MFCControlLadenDialog#42](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_1.cpp)]  
  
    -   コンス トラクターに次のコードを追加します。  
  
         [!code-cpp[NVC_MFCControlLadenDialog#46](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_5.cpp)]  
  
    -   デストラクターには、次のコードを追加します。  
  
         [!code-cpp[NVC_MFCControlLadenDialog#47](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_6.cpp)]  
  
    -   次のコードを追加`OnViewTest`関数を実装します。  
  
         [!code-cpp[NVC_MFCControlLadenDialog#48](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_7.cpp)]  
  
 また、次のサポート技術情報の記事を参照してください。  
  
-   Q251059: HOWTO: MFC ダイアログ ボックスの独自のウィンドウ クラスの名前を指定  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックス](../mfc/dialog-boxes.md)   
 [モーダルとモードレスのダイアログ ボックス](../mfc/modal-and-modeless-dialog-boxes.md)

