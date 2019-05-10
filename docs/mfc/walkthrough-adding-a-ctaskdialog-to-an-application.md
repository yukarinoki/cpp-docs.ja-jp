---
title: 'チュートリアル: アプリケーションへの CTaskDialog の追加'
ms.date: 04/25/2019
helpviewer_keywords:
- CTaskDialog, adding
- walkthroughs [MFC], dialogs
ms.assetid: 3a62abb8-2d86-4bec-bdb8-5784d5f9a9f8
ms.openlocfilehash: 8cf2223b2859a2dfa6ecc7582ec2f171a056152c
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64558196"
---
# <a name="walkthrough-adding-a-ctaskdialog-to-an-application"></a>チュートリアル: アプリケーションへの CTaskDialog の追加

このチュートリアルでは、 [CTaskDialog Class](../mfc/reference/ctaskdialog-class.md) の概要と、そのクラスをアプリケーションに追加する方法について説明します。

`CTaskDialog`は Windows Vista またはそれ以降の Windows メッセージ ボックスを置換するタスク ダイアログ ボックスです。 `CTaskDialog` は Windows メッセージ ボックスを改良したものであり、機能も追加されます。 Windows メッセージ ボックスは、Visual Studio で引き続きサポートされます。

> [!NOTE]
> 前のバージョンの Windows Windows Vista よりも実行をサポートしていません、`CTaskDialog`します。 以前のバージョンの Windows でアプリケーションを実行するユーザーにもメッセージを表示するには、代替のダイアログ ボックス オプションをプログラミングしておく必要があります。 静的メソッドである [CTaskDialog::IsSupported](../mfc/reference/ctaskdialog-class.md#issupported) を使用することで、ユーザーのコンピューターで `CTaskDialog`の Windows メッセージ ボックスに代わるタスク ダイアログ ボックスです。 また、 `CTaskDialog` を使用できるのは、アプリケーションが Unicode ライブラリを使用してビルドされている場合に限られます。

`CTaskDialog` では、情報を収集して表示するためのオプション要素がいくつかサポートされています。 たとえば、 `CTaskDialog` では、コマンド リンク、カスタマイズされたボタン、カスタマイズされたアイコン、およびフッターを表示できます。 さらに、 `CTaskDialog` には、タスク ダイアログ ボックスの状態を照会して、ユーザーが選択したオプション要素を確認するためのメソッドもいくつか用意されています。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを実行するには、次のコンポーネントが必要です。

- Visual Studio 2010 以降

- Windows Vista またはそれ以降

## <a name="replacing-a-windows-message-box-with-a-ctaskdialog"></a>Windows メッセージ ボックスを CTaskDialog に置き換える

次の手順では、 `CTaskDialog`の最も基本的な使用法である、Windows メッセージ ボックスの置き換えについて説明します。 この例では、タスク ダイアログ ボックスに関連付けられているアイコンも変更します。 アイコンの変更により、`CTaskDialog`同じ Windows メッセージ ボックスに表示されます。

### <a name="to-replace-a-windows-message-box-with-a-ctaskdialog"></a>Windows メッセージ ボックスを CTaskDialog に置き換えるには

1. 使用して、 **MFC アプリケーション ウィザード**すべての既定の設定で、MFC アプリケーションを作成します。 「[チュートリアル:新しい MFC シェル コントロールを使用して](walkthrough-using-the-new-mfc-shell-controls.md)Visual Studio のバージョンのウィザードを開く方法の詳細について。

1. 呼び出す*MyProject*します。 

1. **ソリューション エクスプローラー** を使用して、MyProject.cpp ファイルを開きます。

1. 一連の include の末尾に、 `#include "afxtaskdialog.h"` を追加します。

1. `CMyProjectApp::InitInstance`メソッドを探します。 次のコード行を `return TRUE;` ステートメントの前に挿入します。 このコードにより、Windows メッセージ ボックスまたは `CTaskDialog`で使用する文字列が作成されます。

    ```cpp
    CString message("My message to the user");
    CString dialogTitle("My Task Dialog title");
    CString emptyString;
    ```

1. 手順 4. のコードの後に、次のコードを追加します。 このコードによって、ユーザーのコンピューターで `CTaskDialog`がサポートされることが保証されます。 ダイアログ ボックスがサポートされていない場合、アプリケーションが代わりに Windows メッセージ ボックスを表示します。

    ```cpp
    if (CTaskDialog::IsSupported())
    {

    }
    else
    {
        AfxMessageBox(message);
    }
    ```

1. 手順 5. の `if` ステートメントの後にあるかっこ内に、次のコードを挿入します。 このコードによって、 `CTaskDialog`が作成されます。

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

たくない場合は、手順 7. を回避できます、 `CTaskDialog` Windows メッセージ ボックスと同じアイコンを表示します。 その手順を使用しない場合、`CTaskDialog`アプリケーションで表示されるときは、アイコンがありません。

アプリケーションをコンパイルして実行します。 アプリケーションの起動後、タスク ダイアログ ボックスが表示されます。

## <a name="adding-functionality-to-the-ctaskdialog"></a>CTaskDialog に機能を追加する

次の手順では、前の手順で作成した `CTaskDialog` に機能を追加する方法を説明します。 コード例は、ユーザーの選択に基づいて特定の指示を実行する方法を示しています。

### <a name="to-add-functionality-to-the-ctaskdialog"></a>CTaskDialog に機能を追加するには

1. **[リソース ビュー]** 移動します。 表示されない場合、**リソース ビュー**から開くことができます、**ビュー**メニュー。

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

手順 9 でのコードで始まるコメントを置き換える`PROCESS IF`を指定された条件下で実行するコードにします。

アプリケーションをコンパイルして実行します。 新しいコントロールと追加した情報を使用するタスク ダイアログ ボックスが表示されます。

## <a name="displaying-a-ctaskdialog-without-creating-a-ctaskdialog-object"></a>CTaskDialog オブジェクトを作成せずに CTaskDialog を表示する

次の手順では、最初に `CTaskDialog` オブジェクトを作成せずに `CTaskDialog` を表示する方法を説明します。 この例は、前述の手順の続きです。

### <a name="to-display-a-ctaskdialog-without-creating-a-ctaskdialog-object"></a>CTaskDialog オブジェクトを作成せずに CTaskDialog を表示するには

1. まだ開いていない場合は、MyProject.cpp ファイルを開きます。

1. `if (CTaskDialog::IsSupported())` ステートメントの右角かっこにカーソルを移動します。

1. `if` ステートメントの右角かっこの直前 ( `else` ブロックの前) に、次のコードを挿入します。

    ```cpp
    HRESULT result2 = CTaskDialog::ShowDialog(L"My error message",
        L"Error",
        L"New Title",
        TEMP_LINE1,
        TEMP_LINE2);
    ```

アプリケーションをコンパイルして実行します。 2 つのタスク ダイアログ ボックスが表示されます。 最初のダイアログ ボックスが、**機能への CTaskDialog の追加を**プロシージャ; 2 番目のダイアログ ボックスは、前の手順から。

これらの例の使用可能なすべてのオプションを示すしない、 `CTaskDialog`、開始するのに役立ちますが、します。 このクラスの詳細については、「 [CTaskDialog Class](../mfc/reference/ctaskdialog-class.md) 」を参照してください。

## <a name="see-also"></a>関連項目

[ダイアログ ボックス](../mfc/dialog-boxes.md)<br/>
[CTaskDialog クラス](../mfc/reference/ctaskdialog-class.md)<br/>
[CTaskDialog::CTaskDialog](../mfc/reference/ctaskdialog-class.md#ctaskdialog)
