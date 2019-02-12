---
title: ダイアログ ボックス (C++) のコントロールの配置 |Microsoft Docs
ms.date: 11/04/2016
f1_keywords:
- vc.editors.dialog.grouping
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
ms.assetid: 832491cf-98af-42e5-a854-2cb135fd45c6
ms.openlocfilehash: 210fbf8e062b4dd8c469f9c40a015bbc19bc2843
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2019
ms.locfileid: "56152743"
---
# <a name="arrangement-of-controls-on-dialog-boxes-c"></a>ダイアログ ボックス (C++) のコントロールの配置

**ダイアログ**エディターには、整列やコントロールを自動的にサイズ調整されるレイアウト ツールが用意されています。 ほとんどのタスクを使用することができます、[ダイアログ エディター ツールバー](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)します。 すべて**ダイアログ エディター**ツールバーのコマンドはまた、**形式**メニューで、ほとんどが[ショートカット キー](../windows/accelerator-keys-for-the-dialog-editor.md)します。

ダイアログ ボックスのレイアウト コマンドは、1 つ以上のコントロールが選択されている場合にのみ使用可能なは。 単一または複数のコントロールを選択して、1 つ以上のコントロールを選択すると、選択した 1 つ目は既定では「高い」コントロール。 コントロールと主要なコントロールを選択する方法については、次を参照してください。[選択コントロール](../windows/selecting-controls.md)します。

ステータス バーの右上隅には、場所、高さ、および現在のコントロールの幅が表示されます。 全体のダイアログ ボックスがオンの場合、ステータス バーとして全体とその高さと幅 ダイアログ ボックスの位置が表示されます。

## <a name="dialog-editor-states-guides-and-grids"></a>ダイアログ エディターの状態 (ガイドとグリッド)

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

### <a name="create-and-set-guides-and-margins"></a>作成し、ガイドとマージンの設定

コントロールの移動して、コントロールの追加、または現在のレイアウトを並べ替え、ガイドを使用するかどうかは、ダイアログ ボックス内に正確にコントロールを配置します。 ガイドでは、青い点線を表示、エディターの最上部に、左側のルーラーの対応する矢印で表示されるダイアログ ボックスで、**ダイアログ**エディター。

ダイアログ ボックスを作成するときに、次の 4 つの余白が提供されます。 余白は、青い点線として表示される、変更後のガイドです。

|プロセス|手順|
|----------------|----------------|
|ガイドを作成するには|ルーラー、ガイドを作成する 1 回選択します。 (1 回のクリックが新たに作成ガイド; の起動をダブルクリックすると、**番組ガイドの設定** ダイアログ ボックスの番組ガイドの設定を指定することができます)。|
|ガイドを設定するには|ダイアログ ボックスで、ガイドをクリックし、新しい位置にドラッグします。 (できますも矢印をクリックする、ルーラーに関連付けられているガイドをドラッグします。)<br/><br/>ウィンドウの下部にあるステータス バーには、ルーラー、ガイドの座標が表示されます。 ルーラー、ガイドの正確な位置を表示する矢印の上にポインターを移動します。|
|ガイドを削除するには|ダイアログ ボックスには、番組ガイドをドラッグします。<br/><br/>\- または -<br/><br/>ルーラーから対応する矢印をドラッグします。|
|余白を移動するには|余白を新しい位置にドラッグします。<br/><br/>マージンを非表示にするには、余白を 0 の位置に移動します。 余白を元に戻します、余白の位置 0 ポインターを置きます、余白を位置に移動します。|

### <a name="align-controls-on-a-guide"></a>ガイドのコントロールを配置します。

コントロールのサイズ変更ハンドルは、コントロールの移動、およびガイドに合わせてコントロールがない場合、ガイドがコントロールに合わせるときに、ガイドにスナップされます。 ガイドが移動したときにスナップしたコントロールも移動します。 ガイドでは、いずれかが移動すると、コントロールの 1 つ以上のガイドを基準としてスナップされますがサイズ変更されます。

ガイドとコントロールの間隔を決定する定規の目盛りは、ダイアログ単位 (Dlu) によって定義されます。 DLU は、通常、8 ポイント MS Shell Dlg、ダイアログ ボックス フォントのサイズに基づきます。 水平 DLU は、4、ダイアログ ボックスのフォントの平均幅です。 垂直 DLU は 8 で割った値のフォントの高さの平均値です。

#### <a name="to-size-a-group-of-controls-with-guides"></a>ガイドを使用してコントロールのグループのサイズ

1. コントロール (またはコントロール) の一方の側をスナップをガイドします。

1. コントロール (またはコントロール) の反対側のガイドをドラッグします。

   複数のコントロールで必要に応じて、それぞれに 2 番目のガイドへのスナップのサイズします。

1. コントロール (またはコントロール) のサイズのいずれかのガイドに移動します。

#### <a name="to-change-the-intervals-of-the-tick-marks"></a>目盛りの間隔を変更するには

1. **形式** メニューの 選択**ガイド設定**です。

1. **ガイド設定** ダイアログ ボックスで、**グリッドの間隔**フィールドに、Dlu の新しい幅と高さを指定します。

### <a name="disable-guides"></a>ガイドを無効にします。

ガイド、スナップに効果を無効にするのに、マウスと組み合わせて特殊なキーを使用できます。 使用して、 **Alt**キーが選択されているガイドのスナップの効果を無効にします。 ガイドを移動、 **Shift**キーは、スナップしたコントロールが、ガイドに移動しないようにします。

#### <a name="to-disable-the-snapping-effect-of-the-guides"></a>ガイド、スナップに効果を無効にするには

押しながら、コントロールをドラッグ、 **Alt**キー。

#### <a name="to-move-guides-without-moving-the-snapped-controls"></a>スナップしたコントロールを移動せずにガイドを移動するには

押しながら、ガイドをドラッグ、 **Shift**キー。

#### <a name="to-turn-off-the-guides"></a>ガイドでは、オフにするには

1. **形式** メニューの 選択**ガイド設定**です。

1. **ガイド設定**ダイアログ ボックスで、**レイアウト ガイド**を選択します**None**します。

   > [!NOTE]
   > アクセスは、ルーラー バーをダブルクリックすることも、**ガイド設定** ダイアログ ボックス。

\- または -

**形式**メニューの **ガイドの切り替え**します。

### <a name="modify-the-layout-grid"></a>レイアウト グリッドを変更します。

配置またはコントロールの配置 ダイアログ ボックスで、する場合より正確な配置レイアウト グリッドを使用できます。 グリッドをオンにするに「スナップ」グリッドの点線帯びたかのようにコントロールが表示されます。 この「グリッドにスナップ」機能を有効または無効にして、レイアウトのグリッド セルのサイズを変更できます。

#### <a name="to-turn-the-layout-grid-on-or-off"></a>レイアウト グリッドをオンまたはオフにするには

1. **形式** メニューの 選択**ガイド設定**です。

1. **ガイド設定** ダイアログ ボックスをオンまたはオフ、**グリッド**ボタンをクリックします。

   個々 のグリッドでも制御できます**ダイアログ**エディターのウィンドウを使用して、**グリッドの切り替え**ボタンを[ダイアログ エディター ツールバー](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)します。

#### <a name="to-change-the-size-of-the-layout-grid"></a>レイアウト グリッドのサイズを変更するには

1. **形式** メニューの 選択**ガイド設定**です。

1. **ガイド設定** ダイアログ ボックスに、Dlu で、グリッド内のセルの高さと幅を入力します。 最小の高さまたは幅 4 Dlu です。

## <a name="group-radio-buttons-on-a-dialog-box"></a>ダイアログ ボックスにラジオ ボタンをグループ化

ダイアログ ボックスにラジオ ボタンを追加するときに扱うグループとして設定して、**グループ**プロパティ、**プロパティ**グループ内の最初のボタンのウィンドウ。 そのラジオ ボタンのコントロール ID が [メンバー変数の追加ウィザード](../ide/add-member-variable-wizard.md)に表示され、ラジオ ボタンのグループのメンバー変数を追加できるようになります。

1 つのダイアログ ボックスにラジオ ボタンの複数のグループを設定できます。各グループは次の手順を使用して追加する必要があります。

### <a name="to-add-a-group-of-radio-buttons-to-a-dialog-box"></a>ラジオ ボタンのグループをダイアログ ボックスに追加するには

1. ラジオ ボタン コントロールを選択、[ツールボックス ウィンドウ](/visualstudio/ide/reference/toolbox) ダイアログ ボックスで、コントロールを配置する場所を選択します。

1. 手順 1.を繰り返して、必要な数のラジオ ボタンを追加します。 グループ内のラジオ ボタンがタブ オーダーで連続することを確認します。

1. [[プロパティ] ウィンドウ](/visualstudio/ide/reference/properties-window)で、タブ オーダーが **最初** のラジオ ボタンの *[グループ]* プロパティを **[True]** に設定します。

   **[グループ]** プロパティを **[True]** に変更すると、リソース スクリプトのダイアログ オブジェクト内でそのボタンのエントリに WS_GROUP スタイルが追加されます。このため、ユーザーはボタン グループのラジオ ボタンを一度に 1 つしか選べなくなります (ユーザーがラジオ ボタンを 1 つクリックすると、グループの残りのボタンはクリアされます)。

   > [!NOTE]
   > **[グループ]** プロパティを **[True]** に設定する必要があるのは、グループ内の最初のラジオ ボタンだけです。 ボタン グループに属さないその他のコントロールがある場合は、 **グループ以外の** 最初のコントロールの *[グループ]* プロパティも同様に **[True]** に設定します。 キーを押して、グループ外の最初のコントロールをすばやく識別できます**Ctrl**+**D**タブ オーダーを表示します。

### <a name="to-add-a-member-variable-for-the-radio-button-group"></a>ラジオ ボタン グループのメンバー変数を追加するには

1. タブ オーダーの最初のラジオ ボタン コントロール (主要なコントロールであり、 **[グループ]** プロパティが [True] に設定されている) を右クリックします。

1. ショートカット メニューの **[変数の追加]** を選びます。

1. [[メンバー変数の追加ウィザード]](../ide/add-member-variable-wizard.md)で、 **[コントロール変数]** チェック ボックスをオンにして、次に **[値]** ラジオ ボタンを選びます。

1. **[変数名]** ボックスに、新しいメンバー変数の名前を入力します。

1. **変数の型**リスト ボックスで、 **int**または型`int`します。

1. これで、コードを変更し、表示したときに選ばれているラジオ ボタンを指定できます。 たとえば、`m_radioBox1 = 0;`グループ内の最初のラジオ ボタンを選択します。

## <a name="align-groups-of-controls"></a>コントロールのグループを配置します。

次の手順では、コントロールを配置する方法を示します。

### <a name="to-align-groups-of-controls"></a>コントロールのグループを配置するには

1. [コントロールを選択する](../windows/selecting-multiple-controls.md)を配置します。 主要なコントロールを最初にするコントロールを選択することを確認するまたは配置を実行しているか、コマンドのサイズを変更する前に、主要なコントロールに設定します。

   コントロールのグループの最後の位置は、主要なコントロールの位置に依存します。 主要なコントロールを選択する方法の詳細については、次を参照してください。[主要なコントロールを指定する](../windows/specifying-the-dominant-control.md)します。

1. **形式**] メニューの [選択**Align**、以下の配置のいずれかを選択。

   - `Lefts`: 選択したコントロールの左端に揃えて配置します。

   - `Centers`: 選択したコントロールを水平方向の中心点を揃えて配置します。

   - `Rights`: 選択したコントロールの右端に揃えて配置します。

   - `Tops`: 選択したコントロールをそれらの上端に沿って配置します。

   - `Middles`: 選択したコントロールを垂直方向中央の点に配置します。

   - `Bottoms`: 選択したコントロールの下端に揃えて配置します。

### <a name="to-even-the-spacing-between-controls"></a>コントロール間の間隔を均等に

**ダイアログ**等間隔の最も外側のコントロールを選択するエディターを使用します。

1. 配置を変更するコントロールを選択します。

1. **形式**] メニューの [選択**均等スペース**、次の間隔の配置のいずれかを選択します。

   - `Across`: 領域の左端と右端に選択したコントロールの間で均等にコントロール。

   - `Down`: 領域の最上位にある、選択されている最下位のコントロールの間で均等にコントロール。

### <a name="to-center-controls-in-a-dialog-box"></a>ダイアログ ボックスのコントロールの中央に

1. 配置を変更するコントロールを選択します。

1. **形式**] メニューの [選択**ダイアログの中央に**、以下の配置のいずれかを選択します。

   - `Vertical`: ダイアログ ボックスの垂直方向にコントロール センターです。

   - `Horizontal`: ダイアログ ボックスの水平方向にコントロール センターです。

### <a name="to-arrange-push-buttons-along-the-right-or-bottom-of-a-dialog-box"></a>右端またはダイアログ ボックスの下部にあるプッシュ ボタンを配置するには

1. 1 つまたは複数のプッシュ ボタンを選択します。

1. **形式**] メニューの [選択**ボタンの配置**、以下の配置のいずれかを選択します。

   - `Right`: プッシュ ボタン、ダイアログ ボックスの右端に揃えて配置します。

   - `Bottom`: プッシュ ボタン、ダイアログ ボックスの下端に揃えて配置します。

       プッシュ ボタン以外のコントロールを選択した場合の位置に影響を与えません。

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

マネージ プロジェクトにリソースを追加する方法については、次を参照してください。 [Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)<br/>
[コントロール](../mfc/controls-mfc.md)