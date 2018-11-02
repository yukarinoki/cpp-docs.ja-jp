---
title: コントロールのタブ オーダーの変更
ms.date: 11/04/2016
helpviewer_keywords:
- controls [C++], tab order
- focus, tab order
- tab controls [C++], tab order
- Tabstop property for controls
- controls [C++], focus
- dialog box controls [C++], tab order
ms.assetid: e2cee764-4367-42d7-9563-65a68f76f5ff
ms.openlocfilehash: aaff855434ccd8f14b0bbd2394ae2902cf9390b2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429329"
---
# <a name="changing-the-tab-order-of-controls"></a>コントロールのタブ オーダーの変更

タブ オーダーは、順序、**タブ**キーは、ダイアログ ボックス内で [次へ] を 1 つのコントロールから入力フォーカスを移動します。 通常は左右から、上から下 ダイアログ ボックスで、タブ オーダーが続行されます。 各コントロールには、 **Tabstop**コントロールが入力フォーカスを受け取るかどうかを決定するプロパティ。

### <a name="to-set-input-focus-for-a-control"></a>コントロールの入力フォーカスを設定するには

1. [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、 **True**または**False**で、 **Tabstop**プロパティ。

偶数のコントロールがない、 **Tabstop**プロパティに設定**True**タブ オーダーの一部である必要があります。 これがあります。 たとえば、する[アクセス キー (ニーモニック) を定義する](../windows/defining-mnemonics-access-keys.md)のキャプションがないコントロール。 直前に、関連コントロールのアクセス キーを格納した静的テキストは、タブ オーダー内で、関連するコントロールを指定する必要があります。

> [!NOTE]
> ダイアログ ボックスに重複するコントロールが含まれている場合は、タブ オーダーの変更と、コントロールが表示される方法を変更可能性があります。 タブ オーダーの後でコントロールは常に、タブ オーダー内でその前にあるすべての重複するコントロールの上に表示されます。

### <a name="to-view-the-current-tab-order-for-all-controls-in-a-dialog-box"></a>ダイアログ ボックスですべてのコントロールの現在のタブ オーダーを表示するには

1. **形式** メニューのをクリックして**タブ オーダー**します。

\- または -

- キーを押して**Ctrl**+**D**します。

### <a name="to-change-the-tab-order-for-all-controls-in-a-dialog-box"></a>ダイアログ ボックスのすべてのコントロールのタブ オーダーを変更するには

1. **形式** メニューのをクリックして**タブ オーダー**します。

   各コントロールの左上隅にある数では、現在のタブ オーダー内での位置を示します。

2. タブ オーダーを設定する順序で各コントロールをクリックして、**タブ**キーにします。

3. キーを押して**Enter**を終了する**タブ オーダー**モード。

   > [!TIP]
   > 入力すると、**タブ オーダー**モードでは、キーを押して**Esc**または **」と入力**タブ オーダーを変更する機能を無効にします。

### <a name="to-change-the-tab-order-for-two-or-more-controls"></a>2 つまたは複数のコントロールのタブ オーダーを変更するには

1. **形式**] メニューの [選択**タブ オーダー**します。

2. 順序の変更を開始する場所を指定します。 これを行うには、キーを押し、 **ctrl キーを押し**キーし、1 つの変更後の順序で開始する前にコントロールをクリックします。

   例では、コントロールの順序を変更する場合の`7`を通じて`9`を押しながら**Ctrl**、コントロールを選択し、`6`最初。

   > [!NOTE]
   > 数に特定のコントロールを設定する`1`(最初にタブ オーダーにある) コントロールをダブルクリックします。

3. リリース、 **Ctrl**キーをし順序でコントロールをクリックして、**タブ**その時点から次のキー。

4. キーを押して**Enter**を終了する**タブ オーダー**モード。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[ダイアログ ボックスのコントロールの配置](../windows/arrangement-of-controls-on-dialog-boxes.md)<br/>
[ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)<br/>
[コントロール](../mfc/controls-mfc.md)