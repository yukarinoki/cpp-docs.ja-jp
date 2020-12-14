---
description: '詳細については、「方法: Windows フォームコントロールにコマンドルーティングを追加する」を参照してください。'
title: '方法: Windows フォーム コントロールにコマンド ルーティングを追加する'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- command routing [C++], adding to Windows Forms controls
- Windows Forms controls [C++], command routing
ms.assetid: bf138ece-b463-442a-b0a0-de7063a760c0
ms.openlocfilehash: b46087d7df3da5f402432731db4b994b257a385b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335415"
---
# <a name="how-to-add-command-routing-to-the-windows-forms-control"></a>方法: Windows フォーム コントロールにコマンド ルーティングを追加する

[CWinFormsView](../mfc/reference/cwinformsview-class.md) は、コマンドと更新コマンド UI メッセージをユーザーコントロールにルーティングして、MFC コマンドを処理できるようにします (たとえば、フレームメニュー項目やツールバーボタンなど)。

ユーザーコントロールは、次の例に示すように、 [ICommandTarget:: Initialize](../mfc/reference/icommandtarget-interface.md#initialize) を使用して、にコマンドソースオブジェクトへの参照を格納し `m_CmdSrc` ます。 `ICommandTarget` を使用するには、mfcmifc80.dll への参照を追加する必要があります。

`CWinFormsView` は、共通の MFC ビューの通知をマネージド ユーザー コントロールに転送することによって処理します。 これらの通知には、 [OnInitialUpdate](../mfc/reference/iview-interface.md#oninitialupdate)、 [OnUpdate](../mfc/reference/iview-interface.md#onupdate) 、および [onの各ビュー](../mfc/reference/iview-interface.md#onactivateview) メソッドが含まれます。

このトピックでは、「 [方法: ダイアログボックスにユーザーコントロールとホストを作成](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) する」および「 [方法: ユーザーコントロールを作成して MDI ビューをホスト](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)する」を既に完了していることを前提としています。

### <a name="to-create-the-mfc-host-application"></a>MFC ホスト アプリケーションを作成するには

1. [「方法: ダイアログボックスにユーザーコントロールおよびホストを作成](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)する」で作成した Windows フォームコントロールライブラリを開きます。

1. mfcmifc80.dll への参照を追加します。これを行うには、 **ソリューションエクスプローラー** でプロジェクトノードを右クリックし、[ **追加**]、[ **参照**] の順に選択し、Microsoft Visual Studio 10.0 \ VC\atlmfc\lib. を参照します。

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

1. [「方法: ユーザーコントロールを作成し、MDI ビューをホスト](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)する」で作成した MFC アプリケーションを開きます。

1. `singleMenuHandler` を呼び出すメニュー オプションを追加します。

   **リソースビュー** に移動し (Ctrl + Shift + E)、**メニュー** フォルダーを展開し、[ **IDR_MFC02TYPE**] をダブルクリックします。 これにより、メニュー エディターが表示されます。

   [ **表示** ] メニューの下部にメニューオプションを追加します。 [ **プロパティ** ] ウィンドウで、メニューオプションの ID を確認します。 ファイルを保存します。

   **ソリューションエクスプローラー** で、resource.h ファイルを開き、追加したメニューオプションの ID 値をコピーして、その値を C# プロジェクトのメソッドの呼び出しの最初のパラメーターとして貼り付け `m_CmdSrc.AddCommandHandler` `Initialize` ます ( `32771` 必要に応じて置き換えます)。

1. プロジェクトをビルドして実行します。

   **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。

   [ **デバッグ** ] メニューの [ **デバッグなしで開始**] をクリックします。

   追加したメニュー オプションを選択します。 .dll 内のメソッドが呼び出されます。

## <a name="see-also"></a>関連項目

[MFC ビューとしての Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)<br/>
[ICommandSource インターフェイス](../mfc/reference/icommandsource-interface.md)<br/>
[ICommandTarget インターフェイス](../mfc/reference/icommandtarget-interface.md)
