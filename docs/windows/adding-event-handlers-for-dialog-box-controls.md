---
title: ダイアログ ボックス コントロールのイベント ハンドラーの追加 |Microsoft ドキュメント
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
ms.openlocfilehash: bb39e502ccc40531e72f761a414e4088de8b147d
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121123"
---
# <a name="adding-event-handlers-for-dialog-box-controls"></a>ダイアログ ボックス コントロールへのイベント ハンドラーの追加

既にクラスに関連付けられているプロジェクト ダイアログ ボックスでイベント ハンドラーを作成するときに、いくつかのショートカット利用できます。 既定のコントロールの通知イベントまたは該当する Windows メッセージのハンドラーをすばやく作成できます。

## <a name="to-create-a-handler-for-the-default-control-notification-event"></a>既定のコントロールの通知イベントのハンドラーを作成するには

1. コントロールをダブルクリックします。 テキスト エディターが開きます。

2. テキスト エディターで、コントロール通知ハンドラー コードを追加します。

## <a name="to-create-a-handler-for-any-applicable-windows-message"></a>該当する Windows メッセージのハンドラーを作成するには

1. 通知イベントを処理するコントロールをクリックします。

2. [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、 をクリックして、**イベント コントロール**コントロールに関連付けられた一般的な Windows イベントの一覧を表示するボタンをクリックします。 たとえば、標準の**OK**のボタンでは、**に関する** ダイアログ ボックスには、次の通知イベントが一覧表示します。

   - **BN_CLICKED**

   - **BN_DOUBLECLICKED**

   - **BN_KILLFOCUS**

   - **BN_SETFOCUS**

    > [!NOTE]
    > または、ダイアログ ボックスをオンにし、をクリックして、**イベント** ダイアログ ボックスですべてのコントロールの一般的な Windows イベントの一覧を表示するボタンをクリックします。

3. **プロパティ**ウィンドウは、右側の列を処理するイベントの横をクリックし、推奨される通知イベントの名前 (たとえば、 **OnBnClickedOK**ハンドル**BN_CLICKED**).

    > [!NOTE]
    > または、既定のイベント ハンドラー名を選択するのではなく、任意のイベント ハンドラーの名前を指定できます。

   イベントを選択すると、Visual Studio はテキスト エディターが開き、イベント ハンドラーのコードが表示されます。 既定値の次のコードを追加するなど、 **OnBnClickedOK**:

    ```cpp
    void CAboutDlg::OnBnClickedOk(void)
    {
        // TODO: Add your control notification handler code here
    }
    ```

イベント ハンドラーを追加すると、クラス以外のダイアログ ボックスを実装する 1 つを使用する場合、[イベント ハンドラー ウィザード](../ide/event-handler-wizard.md)です。 詳細については、次を参照してください。[イベント ハンドラーを追加する](../ide/adding-an-event-handler-visual-cpp.md)です。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。

### <a name="requirements"></a>必要条件

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
