---
title: '例 : メニュー コマンドによるダイアログ ボックスの表示'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], examples
- MFC dialog boxes [MFC], displaying
- modeless dialog boxes [MFC], displaying
- dialog boxes [MFC], MFC
- modal dialog boxes [MFC], displaying
- examples [MFC], dialog boxes
- menu items [MFC], examples
ms.assetid: e8692549-acd7-478f-9c5e-ba310ce8cccd
ms.openlocfilehash: 830ba27945ce8da2abd52c7f29d786d098113151
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50483487"
---
# <a name="example-displaying-a-dialog-box-via-a-menu-command"></a>例 : メニュー コマンドによるダイアログ ボックスの表示

このトピックには、プロシージャが含まれています。

- メニュー コマンドによって、モーダル ダイアログ ボックスを表示します。

- メニュー コマンドからモードレス ダイアログ ボックスを表示します。

サンプルの両方の手順は、MFC アプリケーションとを作成するアプリケーションでは、 [MFC アプリケーション ウィザード](../mfc/reference/mfc-application-wizard.md)します。

手順は、次の名前と値を使用します。

|アイテム|名前または値|
|----------|-------------------|
|アプリケーション|DisplayDialog|
|メニュー コマンド|[表示] メニューのコマンドをテストします。コマンド ID ID_VIEW_TEST を =|
|ダイアログ ボックス|テスト ダイアログ ボックスクラス CTestDialog; を =ヘッダー ファイル TestDialog.h; を =変数 testdlg、ptestdlg を =|
|コマンド ハンドラー|OnViewTest|

### <a name="to-display-a-modal-dialog-box"></a>モーダル ダイアログ ボックスを表示するには

1. メニュー コマンドを作成します。参照してください[作成メニューやメニュー項目](../windows/creating-a-menu.md)します。

1. ダイアログ ボックスを作成します。参照してください[ダイアログ エディターを起動](../windows/creating-a-new-dialog-box.md)します。

1. ダイアログ ボックスのクラスを追加します。 参照してください[クラスの追加](../ide/adding-a-class-visual-cpp.md)詳細についてはします。

1. **クラス ビュー**、ドキュメント クラス (CDisplayDialogDoc) を選択します。 **[プロパティ]** ウィンドウで、 **[イベント]** ボタンをクリックします。 左側のウィンドウで、メニュー コマンド (ID_VIEW_TEST) の ID をダブルクリックして、**プロパティ**ウィンドウと選択**コマンド**します。 右側のウィンドウで下矢印をクリックし、選択**\<追加 > OnViewTest**します。

   MDI アプリケーションのメインフレームにメニュー コマンドを追加した場合は、代わりに、アプリケーション クラス (CDisplayDialogApp) を選択します。

1. 次の include ステートメント CDisplayDialogDoc.cpp (または CDisplayDialogApp.cpp) を追加、既存の include ステートメントの後。

   [!code-cpp[NVC_MFCControlLadenDialog#42](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_1.cpp)]

1. 次のコードを追加`OnViewTest`機能を実装します。

   [!code-cpp[NVC_MFCControlLadenDialog#43](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_2.cpp)]

### <a name="to-display-a-modeless-dialog-box"></a>モードレス ダイアログ ボックスを表示するには

1. 手順 4. で、ビュー クラス (CDisplayDialogView) を選択します。 ただし、モーダル ダイアログ ボックスを表示する最初の 4 つの手順を実行します。

1. DisplayDialogView.h を編集します。

   - ファースト クラスの宣言の前のダイアログ ボックス クラスを宣言します。

         [!code-cpp[NVC_MFCControlLadenDialog#44](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_3.h)]

   - 属性のパブリック セクションの後に、ダイアログ ボックスへのポインターを宣言します。

         [!code-cpp[NVC_MFCControlLadenDialog#45](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_4.h)]

1. DisplayDialogView.cpp を編集します。

   - 次のステートメントを含める後、既存の include ステートメントを追加します。

         [!code-cpp[NVC_MFCControlLadenDialog#42](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_1.cpp)]

   - コンス トラクターに次のコードを追加します。

         [!code-cpp[NVC_MFCControlLadenDialog#46](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_5.cpp)]

   - デストラクターには、次のコードを追加します。

         [!code-cpp[NVC_MFCControlLadenDialog#47](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_6.cpp)]

   - 次のコードを追加`OnViewTest`機能を実装します。

         [!code-cpp[NVC_MFCControlLadenDialog#48](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_7.cpp)]

## <a name="see-also"></a>関連項目

[ダイアログ ボックス](../mfc/dialog-boxes.md)<br/>
[モーダルとモードレスのダイアログ ボックス](../mfc/modal-and-modeless-dialog-boxes.md)
