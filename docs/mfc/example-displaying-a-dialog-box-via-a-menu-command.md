---
title: '例 : メニュー コマンドによるダイアログ ボックスの表示'
ms.date: 09/07/2019
helpviewer_keywords:
- MFC dialog boxes [MFC], examples
- MFC dialog boxes [MFC], displaying
- modeless dialog boxes [MFC], displaying
- dialog boxes [MFC], MFC
- modal dialog boxes [MFC], displaying
- examples [MFC], dialog boxes
- menu items [MFC], examples
ms.assetid: e8692549-acd7-478f-9c5e-ba310ce8cccd
ms.openlocfilehash: 281fa77f4954691002268d1e597146a615264695
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616035"
---
# <a name="example-displaying-a-dialog-box-via-a-menu-command"></a>例 : メニュー コマンドによるダイアログ ボックスの表示

このトピックでは、次の手順について説明します。

- メニューコマンドを使用してモーダルダイアログボックスを表示します。

- メニューコマンドを使用して、モードレスダイアログボックスを表示します。

どちらのサンプルプロシージャも MFC アプリケーション用であり、 [Mfc アプリケーションウィザード](reference/mfc-application-wizard.md)を使用して作成するアプリケーションで動作します。

この手順では、次の名前と値を使用します。

|Item|名前または値|
|----------|-------------------|
|Application|DisplayDialog|
|メニューコマンド|[表示] メニューの [テスト] コマンドコマンド ID = ID_VIEW_TEST|
|ダイアログ ボックス|[テスト] ダイアログボックスクラス = CTestDialog;ヘッダーファイル = TestDialog. h;Variable = testdlg、ptestdlg|
|コマンドハンドラー|OnViewTest|

### <a name="to-display-a-modal-dialog-box"></a>モーダルダイアログボックスを表示するには

1. メニューコマンドを作成します。「メニュー[またはメニュー項目の作成](../windows/creating-a-menu.md)」を参照してください。

1. ダイアログボックスを作成します。「[ダイアログエディターの開始」を](../windows/creating-a-new-dialog-box.md)参照してください。

1. ダイアログボックスのクラスを追加します。 詳細について[は、「クラスの追加](../ide/adding-a-class-visual-cpp.md)」を参照してください。

1. **クラスビュー**で、ドキュメントクラス (cdisplayの doc) を選択します。 **[プロパティ]** ウィンドウで、 **[イベント]** ボタンをクリックします。 メニューコマンドの ID (ID_VIEW_TEST) をダブルクリックします。 次に、下矢印をクリックし、[ ** \<Add> onviewtest**] を選択します。

   MDI アプリケーションのメインフレームにメニューコマンドを追加した場合は、代わりにアプリケーションクラス (Cdisplayの App) を選択します。

1. 既存の include ステートメントの後に、次の include ステートメントを Cdisplayの Doc .cpp (または cdisplayの App.config) に追加します。

   ```cpp
   #include "TestDialog.h"
   ```

1. 関数を実装するには、に次のコードを追加し `OnViewTest` ます。

   ```cpp
   CTestDialog testdlg;
   testdlg.DoModal();
   ```

### <a name="to-display-a-modeless-dialog-box"></a>モードレスダイアログボックスを表示するには

1. 最初の4つの手順を実行してモーダルダイアログボックスを表示します。ただし、手順 4. のビュークラス (Cdisplayのビュー) を選択します。

1. DisplayDialogView を編集します。 h:

   - 最初のクラス宣言の前にダイアログボックスクラスを宣言します。

   ```cpp
   class CTestDialog;
   ```

   - Attributes public セクションの後に、ダイアログボックスへのポインターを宣言します。

   ```cpp
   CTestDialog* m_pTestDlg;
   ```

1. Displayview を編集します。 .cpp:

   - 既存の include ステートメントの後に、次の include ステートメントを追加します。

   ```cpp
   #include "TestDialog.h"
   ```

   - コンストラクターに次のコードを追加します。

   ```cpp
   m_pTestDlg = NULL;
   ```

   - 次のコードをデストラクターに追加します。

   ```cpp
   delete m_pTestDlg;
   ```

   - 関数を実装するには、に次のコードを追加し `OnViewTest` ます。

   ```cpp
   if (NULL == m_pTestDlg)
   {
      m_pTestDlg = new CTestDialog(this);
      m_pTestDlg->Create(CTestDialog::IDD, this);
   }
   m_pTestDlg->ShowWindow(SW_SHOW);
   ```

## <a name="see-also"></a>関連項目

[ダイアログボックス](dialog-boxes.md)<br/>
[モーダルおよびモードレスのダイアログボックス](modal-and-modeless-dialog-boxes.md)
