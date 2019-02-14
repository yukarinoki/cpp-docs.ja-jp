---
title: アクセスを制御し、値を定義します。
ms.date: 11/04/2016
f1_keywords:
- vc.editors.dialog.combo
helpviewer_keywords:
- access keys [C++], adding
- keyboard shortcuts [C++], controls
- dialog box controls [C++], mnemonics
- access keys [C++], checking
- mnemonics [C++], checking for duplicate
- mnemonics
- mnemonics [C++], dialog box controls
- keyboard shortcuts [C++], uniqueness checking
- Check Mnemonics command
- controls [C++], access keys
- access keys [C++]
- combo boxes [C++], Data property
- controls [C++], testing values in combo boxes
- combo boxes [C++], adding values
- combo boxes [C++], previewing values
- Data property
- combo boxes [C++], testing values
ms.assetid: 60a85435-aa30-4c5c-98b6-42fb045b9eb2
ms.openlocfilehash: 3a885ad57ba05304d51cb45d0b498d81ad37a148
ms.sourcegitcommit: eb2b34a24e6edafb727e87b138499fa8945f981e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "56264856"
---
# <a name="defining-control-access-and-values"></a>アクセスを制御し、値を定義します。

マネージ プロジェクトにリソースを追加する方法については、次を参照してください。 [Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="change-the-tab-order-of-controls"></a>コントロールのタブ オーダーを変更します。

タブ オーダーは、順序、**タブ**キーは、ダイアログ ボックス内で [次へ] を 1 つのコントロールから入力フォーカスを移動します。 通常は左右から、上から下 ダイアログ ボックスで、タブ オーダーが続行されます。 各コントロールには、 **Tabstop**コントロールが入力フォーカスを受け取るかどうかを決定するプロパティ。

### <a name="to-set-input-focus-for-a-control"></a>コントロールの入力フォーカスを設定するには

[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、 **True**または**False**で、 **Tabstop**プロパティ。

偶数のコントロールがない、 **Tabstop**プロパティに設定**True**タブ オーダーの一部である必要があります。 タブの順序は重要で、たとえば、する[アクセス キー (ニーモニック) を定義する](../windows/defining-mnemonics-access-keys.md)のキャプションがないコントロール。 直前に、関連コントロールのアクセス キーを格納した静的テキストは、タブ オーダー内で、関連するコントロールを指定する必要があります。

> [!NOTE]
> ダイアログ ボックスに重複するコントロールが含まれている場合は、タブ オーダーの変更と、コントロールが表示される方法を変更可能性があります。 タブ オーダーの後でコントロールは常に、タブ オーダー内でその前にあるすべての重複するコントロールの上に表示されます。

### <a name="to-view-the-current-tab-order-for-all-controls-in-a-dialog-box"></a>ダイアログ ボックスですべてのコントロールの現在のタブ オーダーを表示するには

**形式**メニューの **タブ オーダー**します。

\- または -

- キーを押して**Ctrl** + **D**します。

### <a name="to-change-the-tab-order-for-all-controls-in-a-dialog-box"></a>ダイアログ ボックスのすべてのコントロールのタブ オーダーを変更するには

1. **形式**メニューの **タブ オーダー**します。

   各コントロールの左上隅にある数では、現在のタブ オーダー内での位置を示します。

1. タブ オーダーを設定する順序で各コントロールをクリックして、**タブ**キーにします。

1. キーを押して**Enter**を終了する**タブ オーダー**モード。

   > [!TIP]
   > 入力すると、**タブ オーダー**モードでは、キーを押して**Esc**または **」と入力**タブ オーダーを変更する機能を無効にします。

### <a name="to-change-the-tab-order-for-two-or-more-controls"></a>2 つまたは複数のコントロールのタブ オーダーを変更するには

1. **形式**] メニューの [選択**タブ オーダー**します。

1. 順序の変更を開始する場所を指定します。 最初にキーを押し、 **Ctrl**キー、コントロールを選択し、変更後の順序で開始する場所を選択します。

   例では、コントロールの順序を変更する場合の`7`を通じて`9`を押しながら**Ctrl**、コントロールを選択し、`6`最初。

   > [!NOTE]
   > 数に特定のコントロールを設定する`1`(最初にタブ オーダーにある) コントロールをダブルクリックします。

1. リリース、 **Ctrl**キーをし順序で、コントロールを選択、**タブ**その時点から次のキー。

1. キーを押して**Enter**を終了する**タブ オーダー**モード。

## <a name="define-mnemonics-access-keys"></a>ニーモニック (アクセス キー) を定義します。

通常、キーボード ユーザーが入力フォーカスを移動 1 つのコントロールからを別のダイアログ ボックスで、**タブ**と**矢印**キー。 ただし、ユーザーを 1 つのキーを押して、コントロールを選択できるようにするアクセス キー (ニーモニックまたは覚えやすい名前) を定義することができます。

### <a name="to-define-an-access-key-for-a-control-with-a-visible-caption-push-buttons-check-boxes-and-radio-buttons"></a>(プッシュ ボタン、チェック ボックス、ラジオ ボタン)、表示されるキャプションを使用して、コントロールのアクセス キーを定義するには

1. ダイアログ ボックスで、コントロールを選択します。

2. [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)の**キャプション**プロパティ、アンパサンドを入力する、コントロールの新しい名前を入力 (`&`) そのコントロールのアクセス キーとして使用文字の前にします。 たとえば、`&Radio1` のようにします。

3. **Enter** キーを押します。

   下線が表示されるキャプションをアクセス キーを示すために表示されます**R**adio1 します。

### <a name="to-define-an-access-key-for-a-control-without-a-visible-caption"></a>表示されるキャプションを持たないコントロールのアクセス キーを定義するには

1. 使用して、コントロールのキャプションを行う、**静的テキスト**を制御、[ツールボックス](/visualstudio/ide/reference/toolbox)します。

2. 静的なテキスト キャプションのアンパサンドを入力します (`&`) へのアクセス キーとして使用文字の前にします。

3. 静的なテキスト コントロールの直前に、コントロールがタブ オーダー内でラベルを付けることを確認します。

ダイアログ ボックス内のすべてのアクセス キーは一意である必要があります。

### <a name="to-check-for-duplicate-access-keys"></a>重複するアクセス キーを確認するには

1. **形式** メニューのをクリックして**ニーモニックの確認**します。

## <a name="add-values-to-a-combo-box-control"></a>コンボ ボックス コントロールに値を追加します。

ある限り、コンボ ボックス コントロールに値を追加することができます、**ダイアログ**エディターが開きます。

> [!TIP]
> コンボ ボックスにすべての値を追加することをお勧め*する前に*でボックスのサイズを変更、**ダイアログ**エディター、またはするには、複合コントロールに表示されるテキストを切り捨てることができます。

### <a name="to-enter-values-into-a-combo-box-control"></a>コンボ ボックス コントロールに値を入力するには

1. クリックして、コンボ ボックス コントロールを選択します。

1. [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、下へスクロールして、**データ**プロパティ。

   > [!NOTE]
   > 種類でグループ化されたプロパティを表示する場合**データ**に表示されます、 **Misc**プロパティ。

1. 値の領域を選択して、**データ**セミコロンで区切られたプロパティと、データ値を入力します。

   > [!NOTE]
   > スペースがドロップダウン リストで項目がアルファベット順に干渉するためには、値の間にスペースを入れないでください。

1. キーを押して**Enter**値の追加が完了したら。

コンボ ボックスのドロップダウン部分を拡大する方法については、次を参照してください。[し、コンボ ボックスのドロップダウン リストのサイズの設定](setting-the-size-of-the-combo-box-and-its-drop-down-list.md)します。

> [!NOTE]
> この手順を使用して、Win32 プロジェクトに値を追加することはできません (、**データ**Win32 プロジェクトのプロパティがグレー)。 Win32 プロジェクトはこの機能を追加するライブラリを持っていないため、プログラムで Win32 プロジェクトを使用してコンボ ボックスに値を追加する必要があります。

### <a name="to-test-the-appearance-of-values-in-a-combo-box"></a>コンボ ボックスで値の外観をテストするには

内の値を入力した後に、**データ**プロパティを選択、**テスト**のボタンでは、[ダイアログ エディター ツールバー](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)します。

   全体の値の一覧を下へスクロールしてみてください。 入力されたとおりに値が表示されます、**データ**プロパティ、**プロパティ**ウィンドウ。 スペルまたは大文字小文字のチェックはありません。

   キーを押して**Esc**に戻る、 ** ダイアログ ボックス**エディター。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)<br/>
[コントロール](../mfc/controls-mfc.md)