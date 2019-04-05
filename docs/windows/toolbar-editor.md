---
title: ツール バー エディター (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.toolbar.F1
- vc.editors.toolbar
- vc.editors.newtoolbarresource
helpviewer_keywords:
- resource editors [C++], Toolbar editor
- editors, toolbars
- toolbars [C++], editing
- Toolbar editor
- toolbars [C++], creating
- Toolbar editor [C++], creating new toolbars
- Insert Resource
- bitmaps [C++], converting to toolbars
- Toolbar editor [C++], converting bitmaps
- toolbars [C++], converting bitmaps
- New Toolbar Resource dialog box [C++]
- buttons [C++], custom toolbars
- toolbar buttons [C++], editing
- buttons
- toolbar buttons [C++], creating
- Toolbar editor [C++], creating buttons
- toolbar buttons [C++], button image
- toolbar buttons [C++], creating
- toolbar buttons (in Toolbar editor)
- toolbar buttons [C++], moving
- Toolbar editor [C++], moving buttons
- Toolbar editor [C++], copying buttons
- toolbars [C++], copying buttons
- toolbar buttons [C++], copying
- toolbar buttons [C++], deleting
- Toolbar editor [C++], deleting buttons
- Toolbar editor [C++], spacing toolbar buttons
- toolbar buttons [C++], space between buttons
- toolbar controls [MFC], command ID
- toolbar buttons [C++], setting properties
- Toolbar editor [C++], toolbar button properties
- command IDs, toolbar buttons
- size, toolbar buttons
- toolbar buttons [C++], setting properties
- Toolbar editor [C++], toolbar button properties
- status bars [C++], active toolbar button text
- command IDs, toolbar buttons
- width, toolbar buttons
- tool tips [C++], adding to toolbar buttons
- "\n in tool tip"
- toolbar buttons [C++], tool tips
- buttons [C++], tool tips
- Toolbar editor [C++], creating tool tips
ms.assetid: aa9f0adf-60f6-4f79-ab05-bc330f15ec43
ms.openlocfilehash: 9d50561c598f17e251425972590c0663efe6e832
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038163"
---
# <a name="toolbar-editor-c"></a>ツール バー エディター (C++)

**ツール バー エディター**ツールバーのリソースを作成し、ツールバーのリソースにビットマップを変換することができます。 **ツール バー エディター**グラフィカルな表示を使用して、ツールバーとほぼ同じに完成したアプリケーションでどのように表示されるがボタンを表示します。

**ツール バー エディター**ウィンドウと同じボタンのイメージの 2 つのビューが表示されます、**イメージ エディター**ウィンドウ。 分割バーは、2 つのペインを区切るし、ペインの相対的なサイズを変更する側に、側からの分割バーをドラッグすることができます。 アクティブなウィンドウでは、選択境界線が表示され、イメージの 2 つのビューはサブジェクト ツールバー。

![ツール バー エディター](../mfc/media/vctoolbareditor.gif "vcToolbarEditor")<br/>
**ツール バー エディター**

**ツール バー エディター**に似ていますが、**イメージ エディター**機能とメニュー項目、グラフィック ツール、および 2 つのビットマップのグリッドは同じです。 メニュー コマンドは、**イメージ**を切り替えるメニュー、**ツール バー エディター**と**イメージ エディター**します。 使用しての詳細については、**グラフィックス**ツールバーで、**色**パレット、または**イメージ**] メニューの [を参照してください[イメージ エディター](../windows/image-editor-for-icons.md)します。

C++ プロジェクトで新しいツールバーを作成するには、ビットマップを変換します。 グラフィック ビットマップからツールバーのボタンのイメージに変換します。 通常はビットマップでは、ボタンごとに 1 つのイメージの 1 つのビットマップ ボタン イメージがいくつか含まれています。 イメージは、既定値は、イメージの高さ、幅 16 ピクセルと、任意のサイズにすることができます。 ボタンのイメージのサイズを指定することができます、**新規ツール バー リソース** ダイアログ ボックスを選択すると**ツール バー エディター**から、**イメージ** メニューの中で、 **イメージ エディター**します。

**新規ツール バー リソース** ダイアログ ボックスでは、C++ プロジェクトのツール バー リソースに追加するボタンの高さと幅を指定できます。 既定では 16 × 15 ピクセルです。

ツールバーを作成するために使用されるビットマップが最大の幅を 2048 に設定した場合、**ボタンの幅**に*512*、4 つのボタンのみがあることができます。 幅を設定する場合*513*、3 つのボタンのみがあることができます。

**新規ツール バー リソース**ダイアログ ボックスには、次のプロパティ。

|プロパティ|説明|
|---|---------------|
|**ボタンの幅**|ツール バー リソースをビットマップ リソースから変換して、ツールバーのボタンの幅を入力する場所を提供します。|
|**ボタンの高さ**|ツール バー リソースをビットマップ リソースから変換して、ツールバーのボタンの高さを入力する場所を提供します。|

> [!NOTE]
> 幅と高さを指定すると、画像がトリミングされ、標準ツールバーの色 (16 色) を使用する色が調整されます。

既定では、新規または空のボタンがツールバーの右端に表示されます。 編集する前に、このボタンを移動できます。 新しいボタンを作成するときに、[編集] ボタンの右側に空白のもう 1 つのボタンが表示されます。 ツールバーを保存するときに、空白のボタンは保存されません。

ツール バー ボタンには、次のプロパティがあります。

|プロパティ|説明|
|--------------|-----------------|
|**ID**|ボタンの ID を定義します。 ドロップダウンの一覧は、一般的な**ID**名。|
|**幅**|ボタンの幅を設定します。 16 ピクセルをお勧めします。|
|**高さ**|ボタンの高さを設定します。 1 つのボタンの高さは、ツールバーのすべてのボタンの高さを変更します。 15 ピクセルをお勧めします。|
|**プロンプト**|ステータス バーに表示されるメッセージを定義します。 追加*\n*名を追加し、**ツールヒント**ツールバーのボタンを。 詳細については、次を参照してください。[ツールヒントを作成する](../windows/creating-a-tool-tip-for-a-toolbar-button.md)します。|

**幅**と**高さ**のすべてのボタンに適用されます。 ツールバーを作成するために使用されるビットマップが 2048 の最大の幅をボタンの幅を設定した場合、 *512*に幅を設定するかどうかは、4 つのボタンである*513*、3 つのボタンのみがあることができます。

## <a name="how-to"></a>方法

**ツール バー エディター**できます。

### <a name="to-create-new-toolbars"></a>新しいツールバーを作成するには

1. **リソース ビュー**を右クリックし、 *.rc*ファイル**リソースの追加**します。 既存のツールバーにある場合、 *.rc*ファイルを右クリックして、**ツールバー**フォルダーと選択**挿入ツールバー**します。

1. **リソースの追加**ダイアログ ボックスで、**ツールバー**で、**リソースの種類**し選択**新規**します。

   プラス記号の場合 (**+**) 横に表示されます、**ツールバー**リソースの種類ツールバーのテンプレートがあることを意味します。 テンプレートの一覧を展開し、テンプレートを選択して、選択、プラス記号を選択します。**新規**します。

### <a name="to-convert-bitmaps-to-toolbar-resources"></a>ビットマップからツールバーのリソースに変換するには

1. 既存のビットマップ リソースを開き、[イメージ エディター](../windows/image-editor-for-icons.md)します。 ビットマップでない場合は、 *.rc*ファイルを右クリックして、 *.rc*ファイル**インポート**に追加するビットマップに移動し、 *.rc*ファイルおよび選択**オープン**します。

1. メニューに移動して**イメージ** > **ツール バー エディター**します。

   **新規ツール バー リソース** ダイアログ ボックスが表示されます。 幅と高さのビットマップに合わせてアイコン イメージを変更することができます。 ツール バー イメージに表示される、**ツール バー エディター**します。

1. 変換を完了するには、コマンドを変更**ID**のボタンを使用して、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。 新しい入力*ID*か、選択、 **ID**ドロップダウン リストから。

   > [!TIP]
   > **プロパティ**ウィンドウにはタイトル バーの画鋲ボタンが含まれていて、これを選択すると、有効または無効に**自動的に隠す**ウィンドウ。 Windows の個々 のプロパティを再度開くことがなく、すべてのツール バー ボタン プロパティを順番に有効にする**自動的に隠す**無効ため、**プロパティ**ウィンドウが静止しています。

   使用して、新しいツールバーのボタンのコマンド Id を変更することも、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。

### <a name="to-manage-toolbar-buttons"></a>ツール バー ボタンを管理するには

#### <a name="to-create-a-new-toolbar-button"></a>新しいツール バー ボタンを作成するには

1. [リソース ビュー](how-to-create-a-resource-script-file.md#create-resources)リソース フォルダーを展開 (たとえば、 *Project1.rc*)。

1. 展開、**ツールバー**フォルダーと選択を編集するツールバーを実行し、次のいずれか。

   - ツールバーの右端にある空白のボタンに ID を割り当てます。 編集することによって行うことができます、 **ID**プロパティ、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。 たとえば、ツール バー ボタンにメニュー オプションと同じ ID を提供したい場合があります。 この場合、ドロップダウン リスト ボックスを使用して、 **ID**のメニュー オプション。

   - 空で、ツールバーの右端にあるボタンを選択します、**ツールバーのビュー**ウィンドウと描画を開始します。 既定のボタンのコマンド ID が割り当てられます (ID_BUTTON\<n >)。

#### <a name="to-add-an-image-to-a-toolbar-as-a-button"></a>ツールバーにボタンとしてイメージを追加するには

1. [リソース ビュー](how-to-create-a-resource-script-file.md#create-resources)ツールバーをダブルクリックして開きます。

1. 次に、ツールバーに追加するには、イメージを開きます。

   > [!NOTE]
   > Visual Studio で、イメージを開く場合で開きます、**イメージ エディター**します。 他のグラフィックス プログラムでイメージを開くこともできます。

1. メニューに移動して**編集** > **コピー**します。

1. ソース ウィンドウの上部にあるその タブを選択して、ツールバーに切り替えます。

1. メニューに移動して**編集** > **貼り付け**します。

   イメージは、ツールバーの [新規] ボタンとして表示されます。

#### <a name="to-move-a-toolbar-button"></a>ツール バー ボタンを移動するには

**ツールバー ビュー**ウィンドウで、ツールバーの新しい位置に移動するボタンをドラッグします。

- 押したまま、ツールバーからボタンをコピー、 **Ctrl**キーと、**ツールバーのビュー**ウィンドウで、ボタンをドラッグするか、新しい位置または場所に、ツールバーの別のツールバー上。

- ツール バー ボタンを削除するには、ツールバー ボタンをクリックし、ツールバーの外にドラッグします。

- を挿入またはツールバーのボタンの間にスペースを削除するには、か、ドラッグしますから、またはいずれかの別の方向に、ツールバーの。

|アクション|手順|
|------|------|
|空白で後にあるボタンの前にスペースを挿入するには|重複、[次へ] ボタンの半分まで下または右ボタンをドラッグします。|
|後にスペースをボタンの前にスペースを挿入してには、、末尾にスペースを保持するには|右端または下端を [次へ] ボタンをタッチだけがまたは重なるようになるまで、ボタンをドラッグします。|
|後にスペースをボタンの前にスペースを挿入し、その次の領域を閉じます|重複、[次へ] ボタンの半分まで下または右ボタンをドラッグします。|
|ツールバーのボタンの間にスペースを削除するには|偶数について [次へ] ボタンと重なるまでは、スペースのもう一方の側にあるボタンに向けた領域の 1 つの側で、ボタンをドラッグします。|

> [!NOTE]
> ドラッグしているボタンの横にある空き領域がないと、ボタンを過去の横にあるボタン、半分以上ドラッグする場合、**ツール バー エディター**ドラッグしているボタンの反対側にスペースを挿入します。

#### <a name="to-change-the-properties-of-a-toolbar-button"></a>ツール バー ボタンのプロパティを変更するには

1. C++ プロジェクトでは、ツール バー ボタンを選択します。

1. 新しい ID を入力、 **ID**プロパティ、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、ドロップダウン リストを使用して、新しいまたは**ID**します。

#### <a name="to-create-a-tool-tip-for-a-toolbar-button"></a>ツール バー ボタンのツールヒントを作成するには

1. ツール バー ボタンを選択します。

1. [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)の**プロンプト**フィールド、およびメッセージが表示されたら、ステータス バーのボタンの説明を追加、追加`\n`とツール ヒントの名前。

たとえばのツール ヒントを参照してください、**印刷**ボタン**ワードパッド**:

1. 開いている**ワードパッド**します。

1. マウス ポインターを合わせ、**印刷**ツール バー ボタンと、word に注意してください`Print`マウス ポインターの下浮動ようになりました。

1. 下部にあるステータス バーを見て、**ワードパッド**ウィンドウとテキストを今すぐ表示通知`Prints the active document`します。

`Print` ツール ヒントの名前と`Prints the active document`ステータス バーのボタンの説明です。

この効果を使用する場合、**ツール バー エディター**、設定、**プロンプト**プロパティを`Prints the active document\nPrint`します。

## <a name="requirements"></a>必要条件

MFC または ATL

## <a name="see-also"></a>関連項目

[リソース エディター](../windows/resource-editors.md)
<!--
[Menus and Other Resources](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)<br/>
[Toolbar Button Properties](../windows/toolbar-button-properties.md)<br/>-->
