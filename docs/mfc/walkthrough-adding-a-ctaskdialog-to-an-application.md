---
title: 'チュートリアル: アプリケーションへの CTaskDialog の追加'
ms.date: 04/25/2019
helpviewer_keywords:
- CTaskDialog, adding
- walkthroughs [MFC], dialogs
ms.assetid: 3a62abb8-2d86-4bec-bdb8-5784d5f9a9f8
ms.openlocfilehash: 3a970df4911fed643045a1c6b59fcda1a853dbcf
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222772"
---
# <a name="walkthrough-adding-a-ctaskdialog-to-an-application"></a>チュートリアル: アプリケーションへの CTaskDialog の追加

このチュートリアルでは、 [CTaskDialog Class](../mfc/reference/ctaskdialog-class.md) の概要と、そのクラスをアプリケーションに追加する方法について説明します。

は、 `CTaskDialog` Windows Vista 以降の windows メッセージボックスに代わるタスクダイアログボックスです。 `CTaskDialog` は Windows メッセージ ボックスを改良したものであり、機能も追加されます。 Visual Studio では、Windows メッセージボックスは引き続きサポートされています。

> [!NOTE]
> Windows Vista より前のバージョンの Windows では、はサポートされていません `CTaskDialog` 。 以前のバージョンの Windows でアプリケーションを実行するユーザーにもメッセージを表示するには、代替のダイアログ ボックス オプションをプログラミングしておく必要があります。 静的メソッドである [CTaskDialog::IsSupported](../mfc/reference/ctaskdialog-class.md#issupported) を使用することで、ユーザーのコンピューターで `CTaskDialog`の Windows メッセージ ボックスに代わるタスク ダイアログ ボックスです。 また、 `CTaskDialog` を使用できるのは、アプリケーションが Unicode ライブラリを使用してビルドされている場合に限られます。

`CTaskDialog` では、情報を収集して表示するためのオプション要素がいくつかサポートされています。 たとえば、 `CTaskDialog` では、コマンド リンク、カスタマイズされたボタン、カスタマイズされたアイコン、およびフッターを表示できます。 さらに、 `CTaskDialog` には、タスク ダイアログ ボックスの状態を照会して、ユーザーが選択したオプション要素を確認するためのメソッドもいくつか用意されています。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを実行するには、次のコンポーネントが必要です。

- Visual Studio 2010 以降

- Windows Vista 以降

## <a name="replacing-a-windows-message-box-with-a-ctaskdialog"></a>Windows メッセージ ボックスを CTaskDialog に置き換える

次の手順では、 `CTaskDialog`の最も基本的な使用法である、Windows メッセージ ボックスの置き換えについて説明します。 この例では、タスク ダイアログ ボックスに関連付けられているアイコンも変更します。 アイコンを変更すると、が `CTaskDialog` Windows メッセージボックスと同じ表示になります。

### <a name="to-replace-a-windows-message-box-with-a-ctaskdialog"></a>Windows メッセージ ボックスを CTaskDialog に置き換えるには

1. **Mfc アプリケーションウィザード**を使用して、すべての既定の設定を含む mfc アプリケーションを作成します。 お使いのバージョンの Visual Studio のウィザードを開く方法については[、「チュートリアル: 新しい MFC シェルコントロールの使用](walkthrough-using-the-new-mfc-shell-controls.md)」を参照してください。

1. *MyProject*を呼び出します。

1. **ソリューション エクスプローラー** を使用して、MyProject.cpp ファイルを開きます。

1. 一連の include の末尾に、 `#include "afxtaskdialog.h"` を追加します。

1. `CMyProjectApp::InitInstance`メソッドを探します。 次のコード行を `return TRUE;` ステートメントの前に挿入します。 このコードにより、Windows メッセージ ボックスまたは `CTaskDialog`で使用する文字列が作成されます。

    ```cpp
    CString message("My message to the user");
    CString dialogTitle("My Task Dialog title");
    CString emptyString;
    ```

1. 手順 4. のコードの後に、次のコードを追加します。 このコードによって、ユーザーのコンピューターで `CTaskDialog`がサポートされることが保証されます。 ダイアログがサポートされていない場合は、代わりに Windows メッセージボックスが表示されます。

    ```cpp
    if (CTaskDialog::IsSupported())
    {

    }
    else
    {
        AfxMessageBox(message);
    }
    ```

1. 手順 5. のステートメントの後にある角かっこの間に次のコードを挿入し **`if`** ます。 このコードによって、 `CTaskDialog`が作成されます。

    ```cpp
    CTaskDialog taskDialog(message, emptyString, dialogTitle, TDCBF_OK_BUTTON);
    ```

1. その次の行に、次のコードを追加します。 このコードによって、警告アイコンが設定されます。

    ```cpp
    taskDialog.SetMainIcon(TD_WARNING_ICON);
    ```

1. その次の行に、次のコードを追加します。 このコードによって、タスク ダイアログ ボックスが表示されます。

    ```cpp
    taskDialog.DoModal();
    ```

が `CTaskDialog` Windows メッセージボックスと同じアイコンを表示しないようにする場合は、手順 7. を避けることができます。 この手順を実行しない場合、には、 `CTaskDialog` アプリケーションが表示したときにアイコンが表示されません。

アプリケーションをコンパイルして実行します。 アプリケーションの起動後、タスク ダイアログ ボックスが表示されます。

## <a name="adding-functionality-to-the-ctaskdialog"></a>CTaskDialog に機能を追加する

次の手順では、前の手順で作成した `CTaskDialog` に機能を追加する方法を説明します。 コード例は、ユーザーの選択に基づいて特定の指示を実行する方法を示しています。

### <a name="to-add-functionality-to-the-ctaskdialog"></a>CTaskDialog に機能を追加するには

1. **[リソース ビュー]** 移動します。 **リソースビュー**が表示されない場合は、[**表示**] メニューから開くことができます。

1. **[リソース ビュー]** を展開して、 **[ストリング テーブル]** フォルダーを選択します。 そのフォルダーを展開し、 **[ストリング テーブル]** エントリをダブルクリックします。

1. ストリング テーブルの一番下までスクロールし、新しいエントリを追加します。 ID を `TEMP_LINE1`に変更します。 キャプションを「 **Command Line 1**」に設定します。

1. 新しいエントリをもう 1 つ追加します。 ID を `TEMP_LINE2`に変更します。 キャプションを「 **Command Line 2**」に設定します。

1. MyProject.cpp に戻ります。

1. `CString emptyString;`の後に、次のコードを追加します。

    ```cpp
    CString expandedLabel("Hide extra information");
    CString collapsedLabel("Show extra information");
    CString expansionInfo("This is the additional information to the user,\nextended over two lines.");
    ```

1. `taskDialog.DoModal()` ステートメントを探し、そのステートメントを次のコードに置き換えます。 このコードによってタスク ダイアログ ボックスが更新され、新しいコントロールが追加されます。

    ```cpp
    taskDialog.SetMainInstruction(L"Warning");
    taskDialog.SetCommonButtons(
        TDCBF_YES_BUTTON | TDCBF_NO_BUTTON | TDCBF_CANCEL_BUTTON);
    taskDialog.LoadCommandControls(TEMP_LINE1, TEMP_LINE2);
    taskDialog.SetExpansionArea(
        expansionInfo, collapsedLabel, expandedLabel);
    taskDialog.SetFooterText(L"This is the a small footnote to the user");
    taskDialog.SetVerificationCheckboxText(L"Remember your selection");
    ```

1. ユーザーにタスク ダイアログ ボックスを表示し、ユーザーの選択内容を取得する次のコード行を追加します。

    ```cpp
    INT_PTR result = taskDialog.DoModal();
    ```

1. 次のコードを `taskDialog.DoModal()`の呼び出しの後に挿入します。 このコード セクションで、ユーザーの入力が処理されます。

    ```cpp
    if (taskDialog.GetVerificationCheckboxState())
    {
        // PROCESS IF the user selects the verification checkbox
    }

    switch (result)
    {
    case TEMP_LINE1:
        // PROCESS IF the first command line
        break;
    case TEMP_LINE2:
        // PROCESS IF the second command line
        break;
    case IDYES:
        // PROCESS IF the user clicks yes
        break;
    case IDNO:
        // PROCESS IF the user clicks no
        break;
    case IDCANCEL:
        // PROCESS IF the user clicks cancel
        break;
    default:
        // This case should not be hit because closing
        // the dialog box results in IDCANCEL
        break;
    }
    ```

手順9のコードで、で始まるコメントを、指定し `PROCESS IF` た条件で実行するコードに置き換えます。

アプリケーションをコンパイルして実行します。 新しいコントロールと追加した情報を使用するタスク ダイアログ ボックスが表示されます。

## <a name="displaying-a-ctaskdialog-without-creating-a-ctaskdialog-object"></a>CTaskDialog オブジェクトを作成せずに CTaskDialog を表示する

次の手順では、最初に `CTaskDialog` オブジェクトを作成せずに `CTaskDialog` を表示する方法を説明します。 この例は、前述の手順の続きです。

### <a name="to-display-a-ctaskdialog-without-creating-a-ctaskdialog-object"></a>CTaskDialog オブジェクトを作成せずに CTaskDialog を表示するには

1. MyProject ファイルがまだ開いていない場合は開きます。

1. `if (CTaskDialog::IsSupported())` ステートメントの右角かっこにカーソルを移動します。

1. ステートメントの右角かっこの直前 **`if`** (ブロックの前) に次のコードを挿入し **`else`** ます。

    ```cpp
    HRESULT result2 = CTaskDialog::ShowDialog(L"My error message",
        L"Error",
        L"New Title",
        TEMP_LINE1,
        TEMP_LINE2);
    ```

アプリケーションをコンパイルして実行します。 2 つのタスク ダイアログ ボックスが表示されます。 最初のダイアログボックスは、 **CTaskDialog プロシージャに機能を追加するため**のです。2番目のダイアログボックスは、最後の手順からのものです。

これらの例では、で使用できるすべてのオプションについては説明しません `CTaskDialog` が、作業を開始するには役立ちます。 このクラスの詳細については、「 [CTaskDialog Class](../mfc/reference/ctaskdialog-class.md) 」を参照してください。

## <a name="see-also"></a>関連項目

[ダイアログボックス](../mfc/dialog-boxes.md)<br/>
[CTaskDialog クラス](../mfc/reference/ctaskdialog-class.md)<br/>
[CTaskDialog:: CTaskDialog](../mfc/reference/ctaskdialog-class.md#ctaskdialog)
