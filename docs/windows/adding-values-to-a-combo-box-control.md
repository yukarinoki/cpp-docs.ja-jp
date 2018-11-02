---
title: コンボ ボックス コントロールへの値の追加
ms.date: 11/04/2016
f1_keywords:
- vc.editors.dialog.combo
helpviewer_keywords:
- combo boxes [C++], Data property
- controls [C++], testing values in combo boxes
- combo boxes [C++], adding values
- combo boxes [C++], previewing values
- Data property
- combo boxes [C++], testing values
ms.assetid: 22a78f98-fada-48b3-90d8-7fa0d8e4de51
ms.openlocfilehash: 5df37a14809a41166b713f946b4f1abc19ea1ff4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570379"
---
# <a name="adding-values-to-a-combo-box-control"></a>コンボ ボックス コントロールへの値の追加

ある限り、コンボ ボックス コントロールに値を追加することができます、**ダイアログ**エディターが開きます。

> [!TIP]
> コンボ ボックスにすべての値を追加することをお勧め*する前に*でボックスのサイズを変更、**ダイアログ**エディター、またはするには、複合コントロールに表示されるテキストを切り捨てることができます。

### <a name="to-enter-values-into-a-combo-box-control"></a>コンボ ボックス コントロールに値を入力するには

1. クリックして、コンボ ボックス コントロールを選択します。

2. [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、下へスクロールして、**データ**プロパティ。

   > [!NOTE]
   > 種類でグループ化されたプロパティを表示する場合**データ**に表示されます、 **Misc**プロパティ。

3. 値の領域をクリックして、**データ**セミコロンで区切られたプロパティと、データ値を入力します。

   > [!NOTE]
   > スペースがドロップダウン リストで項目がアルファベット順に干渉するためには、値の間にスペースを入れないでください。

4. クリックして**Enter**値の追加が完了したら。

コンボ ボックスのドロップダウン部分を拡大する方法については、次を参照してください。[し、コンボ ボックスのドロップダウン リストのサイズの設定](setting-the-size-of-the-combo-box-and-its-drop-down-list.md)します。

> [!NOTE]
> この手順を使用して、Win32 プロジェクトに値を追加することはできません (、**データ**Win32 プロジェクトのプロパティがグレー)。 Win32 プロジェクトはこの機能を追加するライブラリを持っていないため、プログラムで Win32 プロジェクトを使用してコンボ ボックスに値を追加する必要があります。

### <a name="to-test-the-appearance-of-values-in-a-combo-box"></a>コンボ ボックスで値の外観をテストするには

1. 内の値を入力した後に、**データ**プロパティ、 をクリックして、**テスト**のボタンでは、[ダイアログ エディター ツールバー](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)します。

   全体の値の一覧を下へスクロールしてみてください。 入力されたとおりに値が表示されます、**データ**プロパティ、**プロパティ**ウィンドウ。 スペルまたは大文字小文字のチェックはありません。

   キーを押して**Esc**に戻る、 ** ダイアログ ボックス**エディター。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)<br/>
[コントロール](../mfc/controls-mfc.md)