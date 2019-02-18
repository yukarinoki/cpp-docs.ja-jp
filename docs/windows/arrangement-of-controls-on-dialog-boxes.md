---
title: '方法: 配置 (C++) |Microsoft Docs'
ms.date: 02/15/2019
f1_keywords:
- vc.editors.dialog.grouping
- vc.editors.dialog.combo
helpviewer_keywords:
- controls [C++], positioning
- dialog box controls [C++], placement
- Dialog Editor [C++], arranging controls
- Dialog Editor [C++], guides and margins
- guides, clearing
- guides
- dialog box controls [C++], placement
- controls [C++], guides and margins
- guides, creating
- guides, moving
- margins, moving
- DLUs (dialog units)
- controls [C++], aligning
- Dialog Editor [C++], snap to guides
- guides, tick mark interval
- dialog box controls [C++], placement
- guides, aligning controls
- dialog units (DLUs)
- snap to guides (Dialog editor)
- controls [C++], sizing
- tick mark interval in Dialog editor
- controls [C++], snap to guides/grid
- guides, disabling snapping
- controls [C++], snap to guides/grid
- controls [C++], layout grid
- snap to layout grid
- grids, turning on or off
- layout grid in Dialog Editor
- grids, changing size
- grid spacing
- guides, settings
- layout grid in Dialog Editor
- controls [C++], snap to guides/grid
- Guide Settings dialog box (Dialog editor)
- controls [C++], aligning
- controls [C++], positioning
- Space Evenly command
- dialog box controls [C++], placement
- Center in Dialog command
- Arrange Buttons command
- buttons, arranging push buttons in dialog boxes
- push buttons
- member variables, adding to radio button groups
- variables, dialog box control member variables
- dialog box controls [C++], grouping radio buttons
- grouping controls
- radio buttons [C++], grouping on dialog boxes
- controls [C++], tab order
- focus, tab order
- tab controls [C++], tab order
- Tabstop property for controls
- controls [C++], focus
- dialog box controls [C++], tab order
- Dialog Editor [C++], selecting controls
- dominant controls
- dialog box controls [C++], selecting in editor
- controls [C++], selecting
- size, controls
- controls [C++], dominant
- controls [C++], removing from groups
- Dialog Editor [C++], dominant control
- Size to Content command
- size, controls
- text, autosizing controls to fit text
- controls [C++], sizing
- Make Same Size command
- combo boxes, sizing
- list controls [C++], scroll bar width
- CListBox::SetHorizontalExtent
- controls [C++], scroll bar
- scroll bars [C++], displaying in controls
- horizontal scroll bar width
- CListBox class, scroll bar width
- scroll bars [C++], width
ms.assetid: 832491cf-98af-42e5-a854-2cb135fd45c6
ms.openlocfilehash: d9bd73c9cc81b113f222bbc090c62200c93554b2
ms.sourcegitcommit: 24592ba0a38c7c996ffd3d55fe1024231a59ccc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2019
ms.locfileid: "56336632"
---
# <a name="how-to-arrange-controls-c"></a>方法: 配置 (C++)

**ダイアログ**エディターには、整列やコントロールを自動的にサイズ調整されるレイアウト ツールが用意されています。 ほとんどのタスクを使用することができます、[ダイアログ エディター ツールバー](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)します。 すべて**ダイアログ エディター**ツールバーのコマンドはまた、**形式**メニューで、ほとんどが[ショートカット キー](../windows/accelerator-keys-for-the-dialog-editor.md)します。

ダイアログ ボックスのレイアウト コマンドは、1 つ以上のコントロールが選択されている場合にのみ使用可能なは。 単一または複数のコントロールを選択して、1 つ以上のコントロールを選択すると、選択した 1 つ目は既定では「高い」コントロール。 コントロールと主要なコントロールを選択する方法については、次を参照してください。[選択コントロール](../windows/selecting-controls.md)します。

ステータス バーの右上隅には、場所、高さ、および現在のコントロールの幅が表示されます。 全体のダイアログ ボックスがオンの場合、ステータス バーとして全体とその高さと幅 ダイアログ ボックスの位置が表示されます。

## <a name="guides-and-grids"></a>ガイドとグリッド

ダイアログ ボックスのコントロールを配置することができます、**ダイアログ**エディターで次の 3 つの異なる状態のいずれか。

- ガイドとマージン (既定の設定)

- レイアウト グリッドを使用

- スナップや配置機能なし

[ダイアログ エディター ツールバー](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)状態を制御するボタンが含まれています。 状態を変更するには、適切なアイコンを選択します。 使用して、状態を変更することも、**番組ガイドの設定**コマンドを**形式**メニュー。

**ガイド設定**ダイアログ ボックスには、次のプロパティ。

|プロパティ|説明|
|---|---|
|**レイアウト ガイド**|レイアウト ガイドの設定を表示します。|
|**None**|レイアウト ツールを非表示にします。|
|**ルーラーとガイド**|有効な場合は、レイアウト ツールにルーラーを追加します。ガイドは、ルーラーに配置することができます。 既定のガイドは、余白は、ドラッグして移動することができます。 ルーラーのガイドを配置を選択します。 ガイドの上または横に、コントロールが移動したときに「スナップ」を制御します。 接続するいると、コントロールは、ガイドにも移動します。 コントロールがそれぞれの側では、ガイドにアタッチされているし、ガイドを移動、コントロールのサイズを変更します。|
|**グリッド**|レイアウト グリッドを作成します。 新しいコントロールがグリッドに自動的に整列します。|
|**グリッドの間隔**|ダイアログ ボックスの単位 (Dlu) では、グリッドの間隔の設定を表示します。|
|**幅：Dlu**|Dlu でレイアウト グリッドの幅を設定します。 水平 DLU は、4、ダイアログ ボックスのフォントの平均幅です。|
|**Height:Dlu**|Dlu でレイアウト グリッドの高さを設定します。 垂直 DLU は 8 で割った値 ダイアログ ボックスのフォントの高さの平均値です。|

### <a name="to-create-edit-and-delete-guides-and-margins"></a>作成、編集、およびガイドとマージンを削除するには

コントロールの移動して、コントロールの追加、または現在のレイアウトを並べ替え、ガイドを使用するかどうかは、ダイアログ ボックス内に正確にコントロールを配置します。 ガイドでは、青い点線を表示、エディターの最上部に、左側のルーラーの対応する矢印で表示されるダイアログ ボックスで、**ダイアログ**エディター。

ダイアログ ボックスを作成するときに、次の 4 つの余白が提供されます。 余白は、青い点線として表示される、変更後のガイドです。 次の操作を参照してください。

- 内でのルーラー、ガイドを作成するには、ガイドを作成する 1 回選択します。 (1 回のクリックが新たに作成ガイド; の起動をダブルクリックすると、**番組ガイドの設定** ダイアログ ボックスの番組ガイドの設定を指定することができます)。

- ダイアログ ボックスで、ガイドを設定するには、ガイドを選択し、新しい位置にドラッグします。 (選択することできますも矢印、ルーラーに関連付けられているガイドをドラッグします。)ウィンドウの下部にあるステータス バーには、ルーラー、ガイドの座標が表示されます。 ルーラー、ガイドの正確な位置を表示する矢印の上にポインターを移動します。

- 余白を移動するには、新しい位置に余白をドラッグします。 マージンを非表示にするには、余白を 0 の位置に移動します。 余白を元に戻します、余白の位置 0 ポインターを置きます、余白を位置に移動します。

- ガイドを削除するには、 ダイアログ ボックスから、ガイドをドラッグするか、ルーラーから対応する矢印をドラッグします。

### <a name="to-align-controls-on-a-guide"></a>ガイドでコントロールを配置するには

コントロールのサイズ変更ハンドルは、コントロールの移動、およびガイドに合わせてコントロールがない場合、ガイドがコントロールに合わせるときに、ガイドにスナップされます。 ガイドが移動したときにスナップしたコントロールも移動します。 ガイドでは、いずれかが移動すると、コントロールの 1 つ以上のガイドを基準としてスナップされますがサイズ変更されます。

ガイドとコントロールの間隔を決定する定規の目盛りは、ダイアログ単位 (Dlu) によって定義されます。 DLU は、通常、8 ポイント MS Shell Dlg、ダイアログ ボックス フォントのサイズに基づきます。 水平 DLU は、4、ダイアログ ボックスのフォントの平均幅です。 垂直 DLU は 8 で割った値のフォントの高さの平均値です。

#### <a name="to-size-a-group-of-controls-with-guides"></a>ガイドを使用してコントロールのグループのサイズ

1. コントロール (またはコントロール) の一方の側をスナップをガイドします。

1. コントロール (またはコントロール) の反対側のガイドをドラッグします。

   複数のコントロールで必要に応じて、それぞれに 2 番目のガイドへのスナップのサイズします。

1. コントロール (またはコントロール) のサイズのいずれかのガイドに移動します。

#### <a name="to-change-the-intervals-of-the-tick-marks"></a>目盛りの間隔を変更するには

**形式**] メニューの [選択**ガイド設定**、次に、**グリッドの間隔**フィールドに、Dlu の新しい幅と高さを指定します。

### <a name="to-disable-guides"></a>ガイドを無効にするには

ガイド、スナップに効果を無効にするのに、マウスと組み合わせて特殊なキーを使用できます。 使用して、 **Alt**キーが選択されているガイドのスナップの効果を無効にします。 ガイドを移動、 **Shift**キーは、スナップしたコントロールが、ガイドに移動しないようにします。

- ガイド、スナップに効果を無効にするコントロールを押しながらドラッグ、 **Alt**キー。

- スナップしたコントロールを移動することがなくガイドに移動するを押しながら、ガイドをドラッグ、 **Shift**キー。

- ガイドを無効に、**形式**] メニューの [選択**ガイド設定**。 次に、**ガイド設定**ダイアログ ボックスで、**レイアウト ガイド**を選択します**None**します。

   > [!NOTE]
   > アクセスは、ルーラー バーをダブルクリックすることも、**ガイド設定** ダイアログ ボックス。

> [!TIP]
> ガイドを無効のショートカットは、**形式**メニューの **ガイドの切り替え**します。

### <a name="to-modify-the-layout-grid"></a>レイアウト グリッドを変更するには

配置またはコントロールの配置 ダイアログ ボックスで、する場合より正確な配置レイアウト グリッドを使用できます。 グリッドをオンにするに「スナップ」グリッドの点線帯びたかのようにコントロールが表示されます。 この「グリッドにスナップ」機能を有効または無効にして、レイアウトのグリッド セルのサイズを変更できます。

- オンまたはオフ、レイアウト グリッドを有効にするから、**形式**] メニューの [選択**番組ガイドの設定**、し、オンまたはオフ、**グリッド**ボタンをクリックします。

   個々 のグリッドでも制御できます**ダイアログ**エディターのウィンドウを使用して、**グリッドの切り替え**ボタンを[ダイアログ エディター ツールバー](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)します。

- レイアウト グリッドのサイズを変更する、**形式**] メニューの [選択**ガイド設定**、し Dlu で、グリッド内のセルの高さと幅を入力します。 最小の高さまたは幅 4 Dlu です。

## <a name="select-controls"></a>コントロールを選択します。

コントロールのサイズを選択、配置、移動、コピー、または削除したり、およびし操作を完了します。 ほとんどの場合でサイズ変更と配置ツールを使用する 1 つ以上のコントロールを選択する必要があります、[ダイアログ エディター ツールバー](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)します。

コントロールが選択されている、影付きの枠が周囲で実線 (アクティブ) または中空 (非アクティブ) を二乗「サイズ変更ハンドル、」小さいときに選択境界線が表示されます。 複数のコントロールを選択すると主要なコントロールが実線のサイズ変更ハンドルがある白抜きのサイズ変更ハンドルの他のすべての選択したコントロール。

複数のコントロールの配置またはサイズ変更する場合、**ダイアログ**エディターは「主要なコントロール」を使用して、他のコントロールのサイズや配置の方法を決定します。 既定では、主要なコントロールは、選択されている最初のコントロールは。

### <a name="to-select-controls"></a>コントロールを選択するには

1. [ツールボックス ウィンドウ](/visualstudio/ide/reference/toolbox)を選択、**ポインター**ツール。

1. 次の手順のいずれかを使用して、選択を行います。

   - 選択ボックスで、ダイアログ ボックスで選択するコントロールの周囲へのポインターをドラッグします。 マウス ボタンを離すと、すべて内側と、選択ボックスが選択されているを交差を制御します。

   - 押しながら、 **Shift**キーを選択したいコントロールを選択します。

   - 押しながら、 **Ctrl**キーを選択したいコントロールを選択します。

1. 追加またはコントロールを選択したコントロールのグループから削除、キーを押し、 **Shift**キーを追加または削除するコントロールを選択します。

> [!NOTE]
> 押しながら、 **Ctrl**キーと選択範囲内のコントロールを選択するとその選択範囲内の主要なコントロールを制御する、します。

### <a name="to-select-a-dominant-control"></a>主要なコントロールを選択するには

- 押しながら主要なコントロールを指定する、 **Ctrl**キーし、を使用して、サイズやその他のコントロールの場所を制御するコントロールを選択します。*最初*します。

- 主要なコントロールを変更するには、現在選択されているすべてのコントロールの外側を選択して現在の選択をオフにし、最初に、別のコントロールを選択すると、前の手順を繰り返します。

> [!NOTE]
> 主要なコントロールのサイズ変更ハンドルは下位のコントロールのハンドルは白抜き点灯します。 すべてのさらにサイズ変更や配置は、主要なコントロールに基づいています。

## <a name="size-controls"></a>コントロールのサイズ

コントロールのサイズを変更するのにには、サイズ変更ハンドルを使用します。 サイズ変更ハンドルにポインターを置き、ときにコントロールをサイズ変更できる方向を示すために図形を変更します。 アクティブなサイズ変更ハンドルは、solid と、その軸に沿ったコントロールのサイズを変更できないサイズ変更ハンドルが中空の場合は、します。

> [!TIP]
> ガイドまたは余白、コントロールをスナップしてコントロールのサイズを変更することもできます。 または移動することによって 1 つは、制御し、ガイド スナップします。

### <a name="to-size-a-control"></a>コントロールのサイズ

1. コントロールを選択します。

1. コントロールのサイズを変更するサイズ変更ハンドルをドラッグします。

   - 上と横にあるサイズ ハンドルでは、水平方向または垂直方向のサイズを変更します。

   - 角にあるサイズ ハンドルでは、水平および垂直の両方向のサイズを変更します。

   > [!TIP]
   > 押しながら、時にコントロールの 1 つのダイアログ単位 (DLU) を変更すること、 **Shift**キーを使用して、**右**と**ダウン**方向キー。

> [!TIP]
> 内のテキストに合わせてコントロールのサイズを自動的に開き、**形式**メニューか、コントロールを右クリックして選択**コンテンツにサイズ**します。

### <a name="to-make-controls-the-same-size"></a>コントロールを変更するには、同じサイズ

主要なコントロールのサイズに基づいてコントロールのグループのサイズを変更することができます。

1. サイズを変更するコントロールを選択します。

   シリーズの最初に選択コントロールは、主要なコントロールです。 グループ内のコントロールの最終的なサイズは、主要なコントロールのサイズによって異なります。

1. **形式**] メニューの [選択**同じサイズに揃える**、いずれかを選択し、**両方**、**高さ**、または**幅**.

### <a name="combo-box"></a>コンボ ボックス

ダイアログ ボックスを追加すると、コンボ ボックスを調整することができます。 ドロップダウン リスト ボックスのサイズを指定することもできます。 詳細については、次を参照してください。[値コンボ ボックス コントロールを追加](../windows/adding-values-to-a-combo-box-control.md)します。

1. コンボ ボックスの右側にある下矢印ボタンを選択します。

   ![MFC プロジェクト コンボ ボックスの矢印](../mfc/media/vccomboboxarrow.gif "vcComboBoxArrow")

   拡張領域のドロップダウンの一覧をコンボ ボックスのサイズを表示するコントロールの変更の概略です。

1. 下のサイズ変更ハンドルを使用すると、ドロップダウン リストの領域の初期サイズを変更できます。

   ![コンボ&#45;MFC プロジェクトで、ボックスのサイズ変更](../mfc/media/vccomboboxsizing.gif "vcComboBoxSizing")

1. コンボ ボックスのドロップダウン リストの部分を終了するには、もう一度ドロップダウン矢印を選択します。

### <a name="horizontal-scroll-bar"></a>水平スクロール バー

MFC クラスを使用してダイアログ ボックスに水平スクロール バーを使用して、リスト ボックスを追加すると、スクロール バーは、アプリケーションに自動的に表示されません。

最も幅の広い要素の最大の幅を呼び出すことによって設定[CListBox::SetHorizontalExtent](../mfc/reference/clistbox-class.md#sethorizontalextent)コードにします。 この値を設定せず、スクロール バーは表示されません、でも、リスト ボックス内の項目は、ボックスよりも広い場合。

## <a name="align-controls"></a>コントロールを配置します。

1. 配置するコントロールを選択します。 必ず最初に高いにしたいコントロールを選択または配置を実行しているか、コマンドのサイズを変更する前に、主要なコントロールに設定します。

   コントロールのグループの最後の位置は、主要なコントロールの位置に依存します。

1. **形式**] メニューの [選択**Align**、以下の配置のいずれかを選択。

   |アラインメント|説明|
   |-----|-----------|
   |`Lefts`|選択したコントロールの左端に揃えて配置します。|
   |`Centers`|選択したコントロールを水平方向の中心点を配置します。|
   |`Rights`|選択したコントロールの右端に揃えて配置します。|
   |`Tops`|それらの上端に沿った選択したコントロールを配置します。|
   |`Middles`|選択したコントロールを垂直方向中央の点に揃えて配置します。|
   |`Bottoms`|選択したコントロールの下端に揃えて配置します。|

### <a name="to-even-spacing-between-controls"></a>コントロール間の間隔が均等に

**ダイアログ**等間隔の最も外側のコントロールを選択するエディターを使用します。

1. 配置を変更するコントロールを選択します。

1. **形式**] メニューの [選択**均等スペース**、次の間隔の配置のいずれかを選択します。

   |スペース|説明|
   |---|---|
   |`Across`|左端と右端に選択したコントロールの間で均等に容量を制御します。|
   |`Down`|最上位にある、選択されている最下位のコントロール間で均等に容量を制御します。|

### <a name="to-center-controls"></a>コントロールの中央に

1. 配置を変更するコントロールを選択します。

1. **形式**] メニューの [選択**ダイアログの中央に**、以下の配置のいずれかを選択します。

   |配置|説明|
   |---|---|
   |`Vertical`|ダイアログ ボックスの縦方向に center を制御します。|
   |`Horizontal`|ダイアログ ボックスで水平方向に center を制御します。|

### <a name="to-arrange-push-buttons"></a>プッシュ ボタンを配置するには

1. 1 つまたは複数のプッシュ ボタンを選択します。

1. **形式**] メニューの [選択**ボタンの配置**、以下の配置のいずれかを選択します。

   |配置|説明|
   |---|---|
   |`Right`|プッシュ ボタン、ダイアログ ボックスの右端に揃えて配置します。|
   |`Bottom`|プッシュ ボタン、ダイアログ ボックスの下端に揃えて配置します。|

   プッシュ ボタン以外のコントロールを選択した場合の位置に影響を与えません。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)<br/>
[コントロール](../mfc/controls-mfc.md)