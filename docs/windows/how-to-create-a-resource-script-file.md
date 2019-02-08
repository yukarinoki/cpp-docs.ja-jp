---
title: '方法: リソース スクリプト ファイル (C++) の作成します。'
ms.date: 11/04/2016
f1_keywords:
- vc.editors.resource
- vc.resvw.add.MFC
helpviewer_keywords:
- rc files [C++], creating
- .rc files [C++], creating
- resource script files [C++], creating
- resources [C++], viewing
- rc files [C++], viewing resources
- .rc files [C++], viewing resources
- resource script files [C++], viewing resources
- resource script files [C++], opening in text format
- .rc files [C++], opening in text format
- rc files [C++], opening in text format
- rc files [C++], adding MFC support
- .rc files [C++], adding MFC support
- MFC, adding support to resource scripts files
- resource script files [C++], adding MFC support
ms.assetid: 82be732a-cdcd-4a58-8de7-976d1418f86b
ms.openlocfilehash: 9055e0f787c238276d3134c2fa6a8afae0102433
ms.sourcegitcommit: 5a7dbd640376e13379f5d5b2cf66c4842e5e737b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2019
ms.locfileid: "55905681"
---
# <a name="how-to-create-a-resource-script-file-c"></a>方法: リソース スクリプト ファイル (C++) の作成します。

> [!NOTE]
> **リソース エディター** Express エディションでは使用できません。
>
> これは Windows デスクトップ アプリケーションだけに適用できます。 .NET 言語のプロジェクトでは、リソース スクリプト ファイルを使用しません。 詳細については、次を参照してください。[リソース ファイル](../windows/resource-files-visual-studio.md)します。

## <a name="to-create-a-new-resource-script-rc-file"></a>リソース スクリプト (.rc) ファイルを新規作成するには

1. 既存のプロジェクト フォルダーにフォーカスを移す**ソリューション エクスプ ローラー**、たとえば、`MyProject`します。

   > [!NOTE]
   > ソリューション フォルダーを含むプロジェクトのフォルダーと混同しないでください**ソリューション エクスプ ローラー**します。 重点を置く場合、**ソリューション**フォルダーでの選択、**新しい項目の追加**ダイアログ ボックス (手順 3) では別になります。

1. **[プロジェクト]** メニューで **[新しい項目の追加]** を選択します。

1. **新しい項目の追加**ダイアログ ボックスで、 **Visual C**フォルダーを選択し、**リソース ファイル (.rc)** 右側のウィンドウでします。

1. リソース スクリプト ファイルの名前を付けます、**名前**テキストを選択し、**オープン**します。

これで、新しいリソースを [作成](../windows/how-to-create-a-resource.md) して .rc ファイルに追加できます。

> [!NOTE]
> リソース スクリプト (.rc ファイル) を追加できるのは、Visual Studio IDE に読み込まれる既存のプロジェクトだけです。 プロジェクトの外側にあるスタンドアロンの .rc ファイルは作成できません。 [リソース テンプレート](../windows/how-to-use-resource-templates.md) (.rct ファイル) はいつでも作成できます。

## <a name="to-open-a-resource-script-file-outside-of-a-c-project-standalone"></a>C++ プロジェクト (スタンドアロン) の外部のリソース スクリプト ファイルを開く

.rc ファイル内のリソースは、プロジェクトを開かずに表示できます。 ドキュメント ウィンドウで開くことで、.rc ファイルが開きます、[リソース ビュー](../windows/resource-view-window.md)ウィンドウのようなファイルがプロジェクト内で開いているとき)。

> [!NOTE]
> ファイルをスタンドアロンで (プロジェクトの外側で) 開いているときのみ使用できるコマンドがあるため、この違いは重要です。 たとえば、ことができますのみファイルを保存する別の形式で、または別のファイル名としてプロジェクトの外側で、ファイルが開かれたときに (、**名前を付けて保存**コマンドは、プロジェクト内でファイルを開いたときに使用できません)。

### <a name="to-open-an-rc-file-outside-a-project"></a>プロジェクトの外部で .rc ファイルを開くには

1. **ファイル**] メニューの [選択**オープン**を選択し、**ファイル**します。

1. **ファイルを開く** ダイアログ ボックスで、表示、ファイルを強調表示して選択するリソース スクリプト ファイルを移動**オープン**します。

   > [!NOTE]
   > まず、プロジェクトを開く場合 (**ファイル**、**開く**、**プロジェクト**)、いくつかのコマンドを使用可能にすることはできません。 ファイルを "スタンドアロン" で開くと、プロジェクトを先に読み込むことなくファイルを開くことができます。

### <a name="to-open-multiple-rc-files-outside-a-project"></a>プロジェクトの外部で複数の .rc ファイルを開くには

1. 2 つのリソース ファイルをスタンドアロンで開きます。 たとえば、開く`Source1.rc`と`Source2.rc`します。

   1. **ファイル**] メニューの [選択**オープン**を選択し、**ファイル**します。

   1. **ファイルを開く** ダイアログ ボックスで、最初のリソース スクリプト ファイルを開きたいへ移動 (`Source1.rc`)、ファイルを強調表示し、選択、**開く**。

   1. 2 番目の .rc ファイルを開くには、前の手順を繰り返します (`Source2.rc`)。

       2 つの .rc ファイルが別個のドキュメント ウィンドウで開きました。

1. 2 つの .rc ファイルを開いているときに、次の手順に従ってウィンドウを並べて表示すると、両方のファイルを同時に見ることができます。

   - **ウィンドウ**] メニューの [選択**水平タブ グループの新しい**または**垂直タブ グループ**します。

       \- または -

   - .Rc ファイルの 1 つを右クリックし **水平タブ グループの新しい**または**垂直タブ グループ**ショートカット メニューから。

> [!NOTE]
> プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

## <a name="to-open-a-resource-script-file-in-text-format"></a>テキスト形式でリソース スクリプト ファイルを開く

ダイアログ ボックスなどのリソースをそのリソース固有のリソース エディター内で開くことなく、プロジェクトのリソース スクリプト (.rc) ファイルの内容を表示する場合があります。 たとえば、リソース ファイル内のすべてのダイアログ ボックスで文字列を検索する場合に、個別にダイアログ ボックスを開区必要はありません。

> [!NOTE]
> プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

含まれているすべてのリソースを表示し、テキスト エディターでサポートされているグローバルの操作を完了するテキスト形式で簡単にリソース ファイルを開くことができます。

> [!NOTE]
> リソース エディター直接読み取りません .rc または`resource.h`ファイル。 リソース コンパイラがこれらのファイルをコンパイルして、リソース エディターで使用される .aps ファイルにします。 これはコンパイル手順のファイルで、シンボル データのみが格納されます。 通常のコンパイル プロセスと同様に、シンボル以外の情報 (コメントなど) はコンパイル プロセス中に破棄されます。 .aps ファイルと .rc ファイルが一致しなくなると、そのたびに .rc ファイルが再生成されます (たとえば、[保存] を実行すると、リソース エディターによって .rc ファイルと resource.h ファイルが上書きされます)。 リソース自体に対する変更は .rc ファイルに組み込まれたままですが、コメントは .rc ファイルが上書きされると失われます。 コメントを保持する方法については、次を参照してください。[コンパイル時にリソースを含む](../windows/how-to-include-resources-at-compile-time.md)します。

### <a name="to-open-a-resource-script-file-as-text"></a>テキスト形式でリソース スクリプト ファイルを開くには

1. **ファイル**メニュー**オープン**を選択し、**ファイル**します。

1. **ファイルを開く** ダイアログ ボックスで、テキスト形式で表示するリソース スクリプト ファイルに移動します。

1. ファイルを強調表示しで下矢印を選択、**オープン**ボタン (ボタンの右側にあります)。

1. 選択**プログラムから開く**ドロップダウン メニューから。

1. **プログラムから開く**ダイアログ ボックスで、**ソース コード (テキスト) エディター**します。

1. **として開く**ドロップダウン リストで、**テキスト**します。

   リソースが表示されます、**ソース コード**エディター。

\- または -

1. **ソリューション エクスプ ローラー**、.rc ファイルを右クリックします。

1. ショートカット メニューでは、次のように選択します**プログラムから開く...** を選択し、**ソース コード (テキスト) エディター**します。

## <a name="to-add-mfc-support-to-resource-script-files"></a>リソース スクリプト ファイルに MFC サポートを追加するには

通常、Windows を使用して用の MFC アプリケーションをビルドする場合、 [MFC アプリケーション ウィザード](../mfc/reference/mfc-application-wizard.md)ウィザードには、Microsoft Foundation のコア機能を含むファイル (リソース スクリプト (.rc) ファイルを含む) の基本セットが生成されますクラス (MFC)。 ただし、MFC に基づいていない Windows アプリケーション用の .rc ファイルを編集している場合、MFC フレームワークに固有の次の機能は使用できません。

- MFC コード ウィザード

- メニュー プロンプト文字列

- コンボ ボックス コントロールの一覧の内容

- ActiveX コントロールのホスト

ただし、お持ちでない既存の .rc ファイルに MFC サポートを追加することができます。

> [!NOTE]
> 次の手順では、MFC が必要です。

### <a name="to-add-mfc-support-to-rc-files"></a>.rc ファイルに MFC サポートを追加するには

1. リソース スクリプト ファイルを開きます。

1. [リソース ビュー](../windows/resource-view-window.md)、リソース フォルダー (たとえば、MFC.rc など) を強調表示します。

1. [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、設定、 **MFC Mode**プロパティを**True**します。

   > [!NOTE]
   > このフラグを設定するだけでなく、.rc ファイルを MFC プロジェクトの一部にする必要があります。 たとえば、設定するだけ**MFC Mode**に**True** Win32 で .rc ファイルをプロジェクトは指定されていません、MFC 機能のいずれか。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[リソース ファイル](../windows/resource-files-visual-studio.md)<br/>
[リソース エディター](../windows/resource-editors.md)