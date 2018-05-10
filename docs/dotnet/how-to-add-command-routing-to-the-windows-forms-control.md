---
title: '方法: コマンドの追加にルーティングする Windows フォーム コントロール |Microsoft ドキュメント'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- command routing [C++], adding to Windows Forms controls
- Windows Forms controls [C++], command routing
ms.assetid: bf138ece-b463-442a-b0a0-de7063a760c0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4c13b0bedf7c81431449aaed8d4fa8f067cdf3d9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-command-routing-to-the-windows-forms-control"></a>方法: Windows フォーム コントロールにコマンド ルーティングを追加する
[CWinFormsView](../mfc/reference/cwinformsview-class.md) MFC コマンド (たとえば、フレームのメニュー項目やツールバーのボタン) を処理することを許可するユーザー コントロールにコマンドおよび更新コマンド UI メッセージをルーティングします。  
  
 ユーザー コントロールを使用して[ICommandTarget::Initialize](../mfc/reference/icommandtarget-interface.md#initialize)内のコマンド ソース オブジェクトへの参照を格納する`m_CmdSrc`次の例で示すように、します。 `ICommandTarget` を使用するには、mfcmifc80.dll への参照を追加する必要があります。  
  
 `CWinFormsView` は、共通の MFC ビューの通知をマネージ ユーザー コントロールに転送することによって処理します。 これらの通知が含まれて、[フィルターと並べ替え順序](../mfc/reference/iview-interface.md#oninitialupdate)、 [OnUpdate](../mfc/reference/iview-interface.md#onupdate)と[OnActivateView](../mfc/reference/iview-interface.md#onactivateview)メソッドです。  
  
 このトピックでは、終了したと仮定[する方法: ダイアログ ボックスで、ユーザー コントロールとホストを作成](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)と[する方法: ユーザー コントロールとホスト MDI ビューを作成](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)です。  
  
### <a name="to-create-the-mfc-host-application"></a>MFC ホスト アプリケーションを作成するには  
  
1.  作成した Windows フォーム コントロール ライブラリを開く[する方法: ダイアログ ボックスで、ユーザー コントロールとホストを作成する](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)です。  
  
2.  プロジェクト ノードを右クリックして行うことができる mfcmifc80.dll への参照を追加**ソリューション エクスプ ローラー**を選択すると、**追加**、**参照**を参照し、Microsoft Visual Studio 10.0\VC\atlmfc\lib です。  
  
3.  UserControl1.Designer.cs を開いて、次の using ステートメントを追加します。  
  
    ```  
    using Microsoft.VisualC.MFC;  
    ```  
  
4.  また、UserControl1.Designer.cs の次の行を変更します。  
  
    ```  
    partial class UserControl1  
    ```  
  
     変更後は次のようになります。  
  
    ```  
    partial class UserControl1 : System.Windows.Forms.UserControl, ICommandTarget  
    ```  
  
5.  `UserControl1` のクラス定義の最初の行として次の行を追加します。  
  
    ```  
    private ICommandSource m_CmdSrc;  
    ```  
  
6.  次のメソッドの定義を `UserControl1` に追加します (次の手順で、MFC コントロールの ID を作成します)。  
  
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
  
7.  作成した MFC アプリケーションを開く[する方法: ユーザー コントロールとホスト MDI ビューの作成](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)です。  
  
8.  `singleMenuHandler` を呼び出すメニュー オプションを追加します。  
  
     移動して**リソース ビュー** (Ctrl + Shift + E)、展開、**メニュー**フォルダー、およびをダブルクリック **[idr_mfc02type]** です。 これにより、メニュー エディターが表示されます。  
  
     下部にあるメニューのオプションを追加、**ビュー**メニュー。 メニュー オプションの ID を確認、**プロパティ**ウィンドウです。 ファイルを保存します。  
  
     **ソリューション エクスプ ローラー**、Resource.h ファイルを開き、追加したメニュー オプションの ID 値をコピーおよび最初のパラメーターとしてその値を貼り付け、 `m_CmdSrc.AddCommandHandler` c# プロジェクトの呼び出す`Initialize`(に置き換えるメソッド`32771`必要な場合)。  
  
9. プロジェクトをビルドして実行します。  
  
     **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。  
  
     **デバッグ** メニューのをクリックして**デバッグなしで開始**です。  
  
     追加したメニュー オプションを選択します。 .dll 内のメソッドが呼び出されます。  
  
## <a name="see-also"></a>関連項目  
 [MFC ビューとして Windows フォーム ユーザー コントロールをホストしています。](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)   
 [関数のインターフェイス](../mfc/reference/icommandsource-interface.md)   
 [ICommandTarget インターフェイス](../mfc/reference/icommandtarget-interface.md)   
 [CommandHandler](http://msdn.microsoft.com/Library/22096734-e074-4aca-8523-4b15590109f9)