---
title: 作成、移動、および編集ツール バー ボタン (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.toolbar
helpviewer_keywords:
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
ms.assetid: d0f0c6c6-9d7e-42b5-a86a-7558127386e7
ms.openlocfilehash: 2a67123e444ad208eaae74a24b72288f2dbb3bdb
ms.sourcegitcommit: 52c05e10b503e834c443ef11e7ca1987e332f876
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2019
ms.locfileid: "55742701"
---
# <a name="creating-moving-and-editing-toolbar-buttons-c"></a>作成、移動、および編集ツール バー ボタン (C++)

ことができます簡単に作成、移動、コピー、およびツールバーのボタンを編集します。

既定では、新規または空のボタンがツールバーの右端に表示されます。 編集する前に、このボタンを移動できます。 新しいボタンを作成するときに、[編集] ボタンの右側に空白のもう 1 つのボタンが表示されます。 ツールバーを保存するときに、空白のボタンは保存されません。

ツール バー ボタンのプロパティは次のとおりです。

|プロパティ|説明|
|--------------|-----------------|
|**ID**|ボタンの ID を定義します。 ドロップダウンの一覧は、一般的な**ID**名。|
|**Width**|ボタンの幅を設定します。 16 ピクセルをお勧めします。|
|**Height**|ボタンの高さを設定します。 1 つのボタンの高さは、ツールバーのすべてのボタンの高さを変更します。 15 ピクセルをお勧めします。|
|**プロンプト**|ステータス バーに表示されるメッセージを定義します。 \N と名を追加すると、そのツール バー ボタンにツールヒントが追加されます。 詳細については、次を参照してください。[ツールヒントを作成する](../windows/creating-a-tool-tip-for-a-toolbar-button.md)します。|

**幅**と**高さ**のすべてのボタンに適用されます。 ツールバーを作成するために使用するビットマップが 2048 の最大の幅です。 したがって、ボタンの幅を 512 に設定した場合は 4 つのボタンのみができ、513 幅を設定する場合は 3 つのボタンのみができます。

マネージ プロジェクトにリソースを追加する方法については、次を参照してください。 [Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

次の操作を参照してください。

## <a name="to-create-a-new-toolbar-button"></a>新しいツール バー ボタンを作成するには

1. [リソース ビュー](../windows/resource-view-window.md)リソース フォルダーを展開 (たとえば、 *Project1.rc*)。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

1. 展開、**ツールバー**フォルダーと編集にツールバーを選択します。

1. ツールバーの右端にある空白のボタンに ID を割り当てます。 編集することによって行うことができます、 **ID**プロパティ、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。 たとえば、ツール バー ボタンにメニュー オプションと同じ ID を提供したい場合があります。 この場合、ドロップダウン リスト ボックスを使用して、 **ID**のメニュー オプション。

   - または -

   ツールバーの右端にある空白のボタンを選択します (で、**ツールバーのビュー**ウィンドウ) と描画を開始します。 既定のボタンのコマンド ID が割り当てられます (ID_BUTTON\<n >)。

コピーして、新しいボタンのツールバー上にイメージを貼り付けることができます。

## <a name="to-add-an-image-to-a-toolbar-as-a-button"></a>ツールバーにボタンとしてイメージを追加するには

1. [リソース ビュー](../windows/resource-view-window.md)ツールバーをダブルクリックして開きます。

1. 次に、ツールバーに追加するには、イメージを開きます。

   > [!NOTE]
   > Visual Studio で、イメージを開く場合で開きます、**イメージ**エディター。 他のグラフィックス プログラムでイメージを開くこともできます。

1. **編集**] メニューの [選択**コピー**します。

1. ソース ウィンドウの上部にあるその タブを選択して、ツールバーに切り替えます。

1. **編集**] メニューの [選択**貼り付け**します。

   イメージは、ツールバーの [新規] ボタンとして表示されます。

## <a name="to-move-a-toolbar-button"></a>ツール バー ボタンを移動するには

**ツールバー ビュー**ウィンドウで、ツールバーの新しい位置に移動するボタンをドラッグします。

## <a name="to-copy-buttons-from-a-toolbar"></a>ツールバーからボタンをコピーするには

1. 押しながら、 **Ctrl**キー。

1. **ツールバー ビュー**ウィンドウで、ボタンをドラッグするか、新しい位置または場所に、ツールバーの別のツールバー上。

## <a name="to-delete-a-toolbar-button"></a>ツール バー ボタンを削除するには

ツール バー ボタンを選択し、ツールバーの外にドラッグします。

## <a name="to-insert-or-remove-space-between-buttons-on-a-toolbar"></a>挿入またはツールバーのボタンの間にスペースを削除するには

一般に、ボタンの間のスペースを挿入するには、ドラッグ互いからツールバーのします。 スペースを削除するには、互いの方向にドラッグします。

### <a name="to-insert-a-space-before-a-button-that-isnt-followed-by-a-space"></a>空白で後にあるボタンの前にスペースを挿入するには

重複、[次へ] ボタンの半分まで下または右ボタンをドラッグします。

### <a name="to-insert-a-space-before-a-button-that-is-followed-by-a-space-and-to-keep-the-trailing-space"></a>後にスペースをボタンの前にスペースを挿入してには、、末尾にスペースを保持するには

右端または下端を [次へ] ボタンをタッチだけがまたは重なるようになるまで、ボタンをドラッグします。

### <a name="to-insert-a-space-before-a-button-that-is-followed-by-a-space-and-close-up-that-following-space"></a>後にスペースをボタンの前にスペースを挿入し、その次の領域を閉じます

重複、[次へ] ボタンの半分まで下または右ボタンをドラッグします。

### <a name="to-remove-a-space-between-buttons-on-a-toolbar"></a>ツールバーのボタンの間にスペースを削除するには

偶数について [次へ] ボタンと重なるまでは、スペースのもう一方の側にあるボタンに向けた領域の 1 つの側で、ボタンをドラッグします。

   ドラッグしているボタンの横にある空き領域がないと、ボタンを過去の横にあるボタン、半分以上ドラッグする場合、**ツールバー**エディターもして、ボタンの反対側にスペースを挿入しますドラッグします。

## <a name="to-change-the-properties-of-a-toolbar-button"></a>ツール バー ボタンのプロパティを変更するには

1. C++ プロジェクトでは、ツール バー ボタンを選択します。

1. 新しい ID を入力、 **ID**プロパティ、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、ドロップダウン リストを使用して、新しいまたは**ID**します。

## <a name="requirements"></a>必要条件

MFC または ATL

## <a name="see-also"></a>関連項目

[ツール バー エディター](../windows/toolbar-editor.md)
