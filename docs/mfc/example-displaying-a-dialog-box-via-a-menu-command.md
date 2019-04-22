---
title: 例:メニュー コマンドによるダイアログ ボックスを表示します。
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
ms.openlocfilehash: 1e730125e47609f0bf87814b32962336cb752b04
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328273"
---
# <a name="example-displaying-a-dialog-box-via-a-menu-command"></a>例:メニュー コマンドによるダイアログ ボックスを表示します。

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

1. **クラス ビュー**、ドキュメント クラス (CDisplayDialogDoc) を選択します。 **[プロパティ]** ウィンドウで、 **[イベント]** ボタンをクリックします。 左側のウィンドウで、メニュー コマンド (ID_VIEW_TEST) の ID をダブルクリックして、**プロパティ**ウィンドウと選択**コマンド**します。 右側のウィンドウで下矢印をクリックし、選択 **\<追加 > OnViewTest** します。

   MDI アプリケーションのメインフレームにメニュー コマンドを追加した場合は、代わりに、アプリケーション クラス (CDisplayDialogApp) を選択します。

1. 次の include ステートメント CDisplayDialogDoc.cpp (または CDisplayDialogApp.cpp) を追加、既存の include ステートメントの後。

   ```cpp
   #include "TestDialog.h"
   ```

1. 次のコードを追加`OnViewTest`機能を実装します。

   ```cpp
   CTestDialog testdlg;
   testdlg.DoModal();  
   ```

### <a name="to-display-a-modeless-dialog-box"></a>モードレス ダイアログ ボックスを表示するには

1. 手順 4. で、ビュー クラス (CDisplayDialogView) を選択します。 ただし、モーダル ダイアログ ボックスを表示する最初の 4 つの手順を実行します。

1. DisplayDialogView.h を編集します。

   - ファースト クラスの宣言の前のダイアログ ボックス クラスを宣言します。

   ```cpp
   class CTestDialog;
   ```

   - 属性のパブリック セクションの後に、ダイアログ ボックスへのポインターを宣言します。

   ```cpp
   CTestDialog* m_pTestDlg;
   ```

1. DisplayDialogView.cpp を編集します。

   - 次のステートメントを含める後、既存の include ステートメントを追加します。

   ```cpp
   #include "TestDialog.h"
   ```

   - コンス トラクターに次のコードを追加します。

   ```cpp
   m_pTestDlg = NULL;
   ```

   - デストラクターには、次のコードを追加します。

   ```cpp
   delete m_pTestDlg;
   ```

   - 次のコードを追加`OnViewTest`機能を実装します。

   ```cpp
   if (NULL == m_pTestDlg)
   {
      m_pTestDlg = new CTestDialog(this);
      m_pTestDlg->Create(CTestDialog::IDD, this);
   }
   m_pTestDlg->ShowWindow(SW_SHOW); 
   ```

## <a name="see-also"></a>関連項目

[ダイアログ ボックス](../mfc/dialog-boxes.md)<br/>
[モーダルとモードレスのダイアログ ボックス](../mfc/modal-and-modeless-dialog-boxes.md)
