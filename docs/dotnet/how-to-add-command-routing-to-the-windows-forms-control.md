---
title: '方法: Windows フォーム コントロールにコマンド ルーティングを追加する'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- command routing [C++], adding to Windows Forms controls
- Windows Forms controls [C++], command routing
ms.assetid: bf138ece-b463-442a-b0a0-de7063a760c0
ms.openlocfilehash: ad64a12051c22a0cfca99d3ec9c5abef579902f4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365171"
---
# <a name="how-to-add-command-routing-to-the-windows-forms-control"></a>方法: Windows フォーム コントロールにコマンド ルーティングを追加する

[CWinFormsView](../mfc/reference/cwinformsview-class.md)は、コマンドと更新コマンド UI メッセージをユーザー コントロールにルーティングして、MFC コマンド (フレーム メニュー項目やツール バー ボタンなど) を処理できるようにします。

ユーザー コントロールは、次の例に示すように[、ICommandTarget::Initialize](../mfc/reference/icommandtarget-interface.md#initialize)を`m_CmdSrc`使用して、コマンド ソース オブジェクトへの参照を 格納します。 `ICommandTarget` を使用するには、mfcmifc80.dll への参照を追加する必要があります。

`CWinFormsView` は、共通の MFC ビューの通知をマネージド ユーザー コントロールに転送することによって処理します。 これらの通知には、[オンイニシャルアップデート](../mfc/reference/iview-interface.md#oninitialupdate)、[オンアップデート](../mfc/reference/iview-interface.md#onupdate)、および[OnActivateViewメソッドが](../mfc/reference/iview-interface.md#onactivateview)含まれます。

このトピックでは、以前に完了しているユーザーを前提としています[: [方法] ダイアログ ボックスでユーザー コントロールとホストを作成](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)[するおよび方法 : ユーザー コントロールとホスト MDI ビューを作成](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)する 。

### <a name="to-create-the-mfc-host-application"></a>MFC ホスト アプリケーションを作成するには

1. 「[方法 : ダイアログ ボックスでユーザー コントロールとホストを作成する](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)」で作成した Windows フォーム コントロール ライブラリを開きます。

1. **mfcmifc80.dll**への参照を追加します。 **Add** **Reference**

1. UserControl1.Designer.cs を開いて、次の using ステートメントを追加します。

    ```
    using Microsoft.VisualC.MFC;
    ```

1. また、UserControl1.Designer.cs の次の行を変更します。

    ```
    partial class UserControl1
    ```

   これを、次のように変更します。

    ```
    partial class UserControl1 : System.Windows.Forms.UserControl, ICommandTarget
    ```

1. `UserControl1` のクラス定義の最初の行として次の行を追加します。

    ```
    private ICommandSource m_CmdSrc;
    ```

1. 次のメソッドの定義を `UserControl1` に追加します (次の手順で、MFC コントロールの ID を作成します)。

    ```
    public void Initialize (ICommandSource cmdSrc)
    {
       m_CmdSrc = cmdSrc;
       // need ID of control in MFC dialog and callback function
       m_CmdSrc.AddCommandHandler(32771, new CommandHandler (singleMenuHandler));
    }

    private void singleMenuHandler (uint cmdUI)
    {
       // User command handler code
       System.Windows.Forms.MessageBox.Show("Custom menu option was clicked.");
    }
    ```

1. 「方法 : ユーザー[コントロールとホスト MDI ビューを作成する](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)」で作成した MFC アプリケーションを開きます。

1. `singleMenuHandler` を呼び出すメニュー オプションを追加します。

   リソース**ビュー** (Ctrl + Shift + E) に移動し、[**メニュー]** フォルダを展開して **、[IDR_MFC02TYPE]** をダブルクリックします。 これにより、メニュー エディターが表示されます。

   **[表示**] メニューの下部にメニュー オプションを追加します。 **[プロパティ]** ウィンドウのメニュー オプションの ID を確認します。 ファイルを保存します。

   **ソリューション エクスプローラー**で Resource.h ファイルを開き、追加したメニュー オプションの ID 値をコピーし、その値を C# プロジェクトのメソッド`m_CmdSrc.AddCommandHandler`の呼び`Initialize`出しに`32771`最初のパラメーターとして貼り付けます (必要に応じて置換)。

1. プロジェクトをビルドして実行します。

   **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。

   [**デバッグ**] メニューの [**デバッグなしで開始**] をクリックします。

   追加したメニュー オプションを選択します。 .dll 内のメソッドが呼び出されます。

## <a name="see-also"></a>関連項目

[MFC ビューとしての Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)<br/>
[インターフェイス](../mfc/reference/icommandsource-interface.md)<br/>
[インターフェイス](../mfc/reference/icommandtarget-interface.md)
