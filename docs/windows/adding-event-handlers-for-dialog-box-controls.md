---
title: ダイアログ ボックスのコントロールのイベント ハンドラーの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Dialog editor, adding event handlers to controls
- controls [C++], event handlers
- dialog box controls, events
- event handlers, for dialog box controls
ms.assetid: f9c70f24-ea6f-44df-82eb-78a2deaee769
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 589318286c48351e3eae6e3a83f42741a805ce68
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463757"
---
# <a name="adding-event-handlers-for-dialog-box-controls"></a>ダイアログ ボックス コントロールへのイベント ハンドラーの追加

既にクラスに関連付けられているプロジェクト ダイアログ ボックスのイベント ハンドラーを作成するときに、いくつかのショートカットの利用できます。 既定のコントロールの通知イベントまたは該当する Windows メッセージのいずれかのハンドラーをすばやく作成できます。

## <a name="to-create-a-handler-for-the-default-control-notification-event"></a>既定のコントロールの通知イベントのハンドラーを作成するには

1. コントロールをダブルクリックします。 テキスト エディターが開きます。

2. テキスト エディターでは、コントロール通知ハンドラー コードを追加します。

## <a name="to-create-a-handler-for-any-applicable-windows-message"></a>該当する Windows メッセージのハンドラーを作成するには

1. 通知イベントを処理するコントロールをクリックします。

2. [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、 をクリックして、**イベント コントロール**ボタン コントロールに関連付けられている共通の Windows イベントの一覧を表示します。 たとえば、標準的な**ok**ボタンを**について** ダイアログ ボックスには、次の通知イベントが一覧表示します。

   - BN_CLICKED

   - BN_DOUBLECLICKED

   - BN_KILLFOCUS

   - BN_SETFOCUS

    > [!NOTE]
    > または、ダイアログ ボックスをオンにし、をクリックして、**イベント** ダイアログ ボックスで、すべてのコントロールの一般的な Windows イベントの一覧を表示するボタンをクリックします。

3. **プロパティ**ウィンドウで、右側の列を処理するイベントをクリックしますと推奨される通知イベントの名前を選択します (たとえば、 **OnBnClickedOK**ハンドル**BN_CLICKED。**).

    > [!NOTE]
    > または、既定のイベント ハンドラー名を選択するのではなく、お好きのイベント ハンドラーの名前を指定できます。

   イベントを選択すると、Visual Studio はテキスト エディターが開き、イベント ハンドラーのコードが表示されます。 既定の次のコードを追加するなど、 **OnBnClickedOK**:

    ```cpp
    void CAboutDlg::OnBnClickedOk(void)
    {
        // TODO: Add your control notification handler code here
    }
    ```

イベント ハンドラー クラスに追加以外のダイアログ ボックスを実装する 1 つを使用する場合、[イベント ハンドラー ウィザード](../ide/event-handler-wizard.md)します。 詳細については、次を参照してください。[イベント ハンドラーの追加](../ide/adding-an-event-handler-visual-cpp.md)します。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド。* マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

### <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[既定のコントロール イベント](../windows/default-control-events.md)  
[ダイアログ コントロールのメンバー変数の定義](../windows/defining-member-variables-for-dialog-controls.md)  
[ダイアログ ボックス コントロールおよび変数の型](../ide/dialog-box-controls-and-variable-types.md)  
[クラスの追加](../ide/adding-a-class-visual-cpp.md)  
[メンバー関数の追加](../ide/adding-a-member-function-visual-cpp.md)  
[メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md)  
[仮想関数のオーバーライド](../ide/overriding-a-virtual-function-visual-cpp.md)  
[MFC メッセージ ハンドラー](../mfc/reference/adding-an-mfc-message-handler.md)  