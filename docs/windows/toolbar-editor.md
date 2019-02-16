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
ms.openlocfilehash: 7ef08551960c9308a84b9838249a3d9ff4950d98
ms.sourcegitcommit: 470de1337035dd33682d935b4b6c6d8b1bdb0bbb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2019
ms.locfileid: "56320615"
---
# <a name="toolbar-editor-c"></a>ツール バー エディター (C++)

**ツールバー**エディターでは、C++ のツールバーのリソースを作成し、ビットマップをツール バー リソースに変換することができます。 **ツールバー**エディターでは、グラフィカルな表示を使用して、ツールバーとほぼ同じに完成したアプリケーションでどのように表示されるがボタンを表示します。

**ツールバー**エディター ウィンドウには、イメージ エディター ウィンドウと同じボタンのイメージの 2 つのビューが表示されます。 分割バーは、2 つのペインを分割します。 分割バーを左右にドラッグすると、ペインの相対サイズを変更できます。 アクティブなペインには、選択境界線が表示されます。 イメージの 2 つのビューの上にはサブジェクト ツールバーがあります。

![ツール バー エディター](../mfc/media/vctoolbareditor.gif "vcToolbarEditor")ツール バー エディター

**ツールバー**エディターと似ています、**イメージ**エディターの機能です。 メニュー項目、グラフィック ツール、およびビットマップのグリッドは、内のものと同じ、**イメージ**エディター。 メニュー コマンドは、**イメージ**メニュー間を切り替えることができるように、**ツールバー**エディターと**イメージ**エディター。 使用しての詳細については、**グラフィックス**ツールバーで、**色**パレット、または**イメージ**] メニューの [を参照してください[イメージ エディター](../windows/image-editor-for-icons.md)します。

C++ プロジェクトで新しいツールバーを作成するには、ビットマップを変換します。 グラフィック ビットマップからツールバーのボタンのイメージに変換します。 通常はビットマップでは、ボタンごとに 1 つのイメージの 1 つのビットマップ ボタン イメージがいくつか含まれています。 イメージは、既定値は、イメージの高さ、幅 16 ピクセルと、任意のサイズにすることができます。 ボタンのイメージのサイズを指定することができます、**新規ツール バー リソース** ダイアログ ボックスを選択すると**ツール バー エディター**から、**イメージ**イメージ エディターでのメニュー。

**新規ツール バー リソース** ダイアログ ボックスでは、C++ プロジェクトのツール バー リソースに追加するボタンの高さと幅を指定できます。 既定では 16 × 15 ピクセルです。

ツールバーを作成するために使用するビットマップが 2048 の最大の幅です。 設定した場合は、**ボタンの幅**512 には、4 つのボタンのみができます。 513 幅を設定する場合は、3 つのボタンのみができます。

ダイアログ ボックスには、次のプロパティ。

|プロパティ|説明|
|---|---|
|**ボタンの幅**|ツール バー リソースをビットマップ リソースから変換して、ツールバーのボタンの幅を入力する場所を提供します。 幅と高さを指定すると、画像がトリミングされ、標準ツールバーの色 (16 色) を使用する色が調整されます。|
|**ボタンの高さ**|ツール バー リソースをビットマップ リソースから変換して、ツールバーのボタンの高さを入力する場所を提供します。 幅と高さを指定すると、画像がトリミングされ、標準ツールバーの色 (16 色) を使用する色が調整されます。|

既定では、新規または空のボタンがツールバーの右端に表示されます。 編集する前に、このボタンを移動できます。 新しいボタンを作成するときに、[編集] ボタンの右側に空白のもう 1 つのボタンが表示されます。 ツールバーを保存するときに、空白のボタンは保存されません。

ツール バー ボタンのプロパティは次のとおりです。

|プロパティ|説明|
|--------------|-----------------|
|**ID**|ボタンの ID を定義します。 ドロップダウンの一覧は、一般的な**ID**名。|
|**Width**|ボタンの幅を設定します。 16 ピクセルをお勧めします。|
|**Height**|ボタンの高さを設定します。 1 つのボタンの高さは、ツールバーのすべてのボタンの高さを変更します。 15 ピクセルをお勧めします。|
|**プロンプト**|ステータス バーに表示されるメッセージを定義します。 \N と名を追加すると、そのツール バー ボタンにツールヒントが追加されます。 詳細については、次を参照してください。[ツールヒントを作成する](../windows/creating-a-tool-tip-for-a-toolbar-button.md)します。|

**幅**と**高さ**のすべてのボタンに適用されます。 ツールバーを作成するために使用するビットマップが 2048 の最大の幅です。 したがって、ボタンの幅を 512 に設定した場合は 4 つのボタンのみができ、513 幅を設定する場合は 3 つのボタンのみができます。

## <a name="how-to"></a>操作方法

**ツールバー**エディターを使用できます。

### <a name="to-create-new-toolbars"></a>新しいツールバーを作成するには

1. **リソース**表示、.rc ファイルを右クリックし **リソースの追加**ショートカット メニューから。 (単に右クリックできる場合は、.rc ファイル内の既存のツールバーにある場合は、**ツールバー**フォルダーと選択**挿入ツールバー**ショートカット メニューから)。

1. **リソースの追加**ダイアログ ボックスで、**ツールバー**で、**リソースの種類**し選択**新規**します。

   プラス記号の場合 (**+**) 横に表示されます、**ツールバー**リソースの種類ツールバーのテンプレートがあることを意味します。 テンプレートの一覧を展開し、テンプレートを選択して、選択、プラス記号を選択します。**新規**します。

### <a name="to-convert-bitmaps-to-toolbar-resources"></a>ビットマップからツールバーのリソースに変換するには

1. 既存のビットマップ リソースを開き、[イメージ エディター](../windows/image-editor-for-icons.md)します。 (.Rc ファイルに、ビットマップがいない場合は、.rc ファイルを右クリックし、選択**インポート**、ショートカット メニューから .rc ファイルに追加するビットマップに移動し、選択**オープン**)。

1. **イメージ**] メニューの [選択**ツール バー エディター**します。

   **新規ツール バー リソース** ダイアログ ボックスが表示されます。 幅と高さのビットマップに合わせてアイコン イメージを変更することができます。 ツールバー エディターで、ツール バー イメージが表示されます。

1. 変換を完了するには、コマンドを変更**ID**のボタンを使用して、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。 新しい入力**ID**か、選択、 **ID**ドロップダウン リストから。

   > [!TIP]
   > **プロパティ**ウィンドウにはタイトル バーの画鋲ボタンが含まれています。 このボタンを選択すると、有効または無効に**自動的に隠す**ウィンドウ。 有効にする個々 のプロパティ ウィンドウを再び開くことがなく、すべてのツール バー ボタン プロパティをすばやく切り替える、**自動的に隠す**オフため、**プロパティ**ウィンドウが静止したままになります。

使用して、新しいツールバーのボタンのコマンド Id を変更することも、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。

### <a name="to-create-move-and-edit-toolbar-buttons"></a>作成するには、移動、およびツール バー ボタンの編集

簡単に作成、移動、コピー、してツール バー ボタンの編集します。

#### <a name="to-create-a-new-toolbar-button"></a>新しいツール バー ボタンを作成するには

1. [リソース ビュー](../windows/resource-view-window.md)リソース フォルダーを展開 (たとえば、 *Project1.rc*)。

1. 展開、**ツールバー**フォルダーと編集にツールバーを選択します。

1. ツールバーの右端にある空白のボタンに ID を割り当てます。 編集することによって行うことができます、 **ID**プロパティ、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。 たとえば、ツール バー ボタンにメニュー オプションと同じ ID を提供したい場合があります。 この場合、ドロップダウン リスト ボックスを使用して、 **ID**のメニュー オプション。

   - または -

   ツールバーの右端にある空白のボタンを選択します (で、**ツールバーのビュー**ウィンドウ) と描画を開始します。 既定のボタンのコマンド ID が割り当てられます (ID_BUTTON\<n >)。

コピーして、新しいボタンのツールバー上にイメージを貼り付けることができます。

#### <a name="to-add-an-image-to-a-toolbar-as-a-button"></a>ツールバーにボタンとしてイメージを追加するには

1. [リソース ビュー](../windows/resource-view-window.md)ツールバーをダブルクリックして開きます。

1. 次に、ツールバーに追加するには、イメージを開きます。

   > [!NOTE]
   > Visual Studio で、イメージを開く場合で開きます、**イメージ**エディター。 他のグラフィックス プログラムでイメージを開くこともできます。

1. **編集**] メニューの [選択**コピー**します。

1. ソース ウィンドウの上部にあるその タブを選択して、ツールバーに切り替えます。

1. **編集**] メニューの [選択**貼り付け**します。

   イメージは、ツールバーの [新規] ボタンとして表示されます。

#### <a name="to-move-a-toolbar-button"></a>ツール バー ボタンを移動するには

**ツールバー ビュー**ウィンドウで、ツールバーの新しい位置に移動するボタンをドラッグします。

#### <a name="to-copy-buttons-from-a-toolbar"></a>ツールバーからボタンをコピーするには

1. 押しながら、 **Ctrl**キー。

1. **ツールバー ビュー**ウィンドウで、ボタンをドラッグするか、新しい位置または場所に、ツールバーの別のツールバー上。

#### <a name="to-delete-a-toolbar-button"></a>ツール バー ボタンを削除するには

ツール バー ボタンを選択し、ツールバーの外にドラッグします。

#### <a name="to-insert-or-remove-space-between-buttons-on-a-toolbar"></a>挿入またはツールバーのボタンの間にスペースを削除するには

一般に、ボタンの間のスペースを挿入するには、ドラッグ互いからツールバーのします。 スペースを削除するには、互いの方向にドラッグします。

|アクション|手順|
|------|------|
|空白で後にあるボタンの前にスペースを挿入するには|重複、[次へ] ボタンの半分まで下または右ボタンをドラッグします。|
|後にスペースをボタンの前にスペースを挿入してには、、末尾にスペースを保持するには|右端または下端を [次へ] ボタンをタッチだけがまたは重なるようになるまで、ボタンをドラッグします。|
|後にスペースをボタンの前にスペースを挿入し、その次の領域を閉じます|重複、[次へ] ボタンの半分まで下または右ボタンをドラッグします。|
|ツールバーのボタンの間にスペースを削除するには|偶数について [次へ] ボタンと重なるまでは、スペースのもう一方の側にあるボタンに向けた領域の 1 つの側で、ボタンをドラッグします。|

> [!NOTE]
> ドラッグしているボタンの横にある空き領域がないと、ボタンを過去の横にあるボタン、半分以上ドラッグする場合、**ツールバー**エディターもして、ボタンの反対側にスペースを挿入しますドラッグします。

#### <a name="to-change-the-properties-of-a-toolbar-button"></a>ツール バー ボタンのプロパティを変更するには

1. C++ プロジェクトでは、ツール バー ボタンを選択します。

1. 新しい ID を入力、 **ID**プロパティ、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、ドロップダウン リストを使用して、新しいまたは**ID**します。

#### <a name="to-create-a-tool-tip-for-a-toolbar-button"></a>ツール バー ボタンのツールヒントを作成するには

1. ツール バー ボタンを選択します。

1. [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)の**プロンプト**プロパティ フィールドをステータス バーのメッセージが表示されたら、ボタンの説明を追加、`\n`とツール ヒントの名前。

ツール ヒントの一般的な例は、**印刷**ボタン**ワードパッド**:

1. 開いている**ワードパッド**します。

1. マウス ポインターを合わせ、**印刷**ツールバー ボタンをクリックします。

1. 注意して、word`Print`マウス ポインターの下浮動ようになりました。

1. ステータス バーを見て (の下部にある、**ワードパッド**ウィンドウ) のようになりました、テキストを表示することが通知`Prints the active document`します。

`Print`で**手順 3** 「ツール ヒント名」は、および`Prints the active document`から**手順 4** 「の説明、ステータス バーのボタンをクリックします」。

この効果を使用する場合、**ツールバー**エディター、設定、**プロンプト**プロパティを`Prints the active document\nPrint`します。

> [!NOTE]
> プロンプトのテキストを使用して編集することができます、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。

## <a name="requirements"></a>必要条件

MFC または ATL

## <a name="see-also"></a>関連項目

[リソース エディター](../windows/resource-editors.md)<br/>
[メニューとその他のリソース](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)<br/>
[ツール バー ボタンのプロパティ](../windows/toolbar-button-properties.md)<br/>
