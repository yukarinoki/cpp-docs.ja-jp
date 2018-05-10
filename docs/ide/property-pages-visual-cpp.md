---
title: プロパティ ページ (Visual C) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.NotAProp.Edit
dev_langs:
- C++
helpviewer_keywords:
- project-file macro
- project properties [C++], default values
- user-defined values
- project properties [C++], setting
- macros, project-file
- property pages, project settings
- Visual C++ projects, properties
- build macro
- user-defined macros
ms.assetid: 13ffe3ea-1bc3-4bee-be5e-053a8a99cce4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1dc831dff6d1e3dbef4fc762712e8125a5b20e1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="property-pages-visual-c"></a>プロパティ ページ (Visual C++)

プロパティ ページを使用することで、Visual Studio プロジェクトの設定を指定できます。 開くには、**プロパティ ページ** ダイアログ ボックス、Visual Studio のプロジェクトで、**プロジェクト** メニューの 選択**プロパティ**です。

すべてのビルド構成に適用されるようにプロジェクト設定を指定することや、ビルド構成ごとに異なるプロジェクト プロパティを指定することができます。 たとえば、リリース構成の設定や、その他のデバッグ構成の設定を指定することができます。

使用可能なすべてのページが表示されるとは限りません、**プロパティ ページ** ダイアログ ボックス。 表示されるページは、プロジェクト内のファイルの種類によって異なります。

詳細については、次を参照してください。[のプロジェクト プロパティの操作](../ide/working-with-project-properties.md)です。

非 Windows プロジェクトでは、次を参照してください。 [Linux C++ プロパティのページ参照](../linux/prop-pages-linux.md)<!-- or [C++ Cross Platform Property Page Reference](../linux/prop-pages-linux.md)-->です。

## <a name="default-properties-vs-modified-properties"></a>既定のプロパティと変更されたプロパティの比較

使用すると、**新しいプロジェクト**、Visual Studio プロジェクトを作成する ダイアログ ボックスでは、指定されたプロジェクト テンプレートを使用して、プロジェクトのプロパティを初期化します。 そのため、テンプレート内のプロパティ値は、そのプロジェクトの種類の既定値と見なすことができます。 他のプロジェクトの種類では、プロパティの既定値が異なる場合があります。

プロジェクト プロパティ値は、変更されている場合は太字で表示されます。 プロジェクト プロパティは、次に示す理由によって変更される場合があります。

- アプリケーション ウィザードが、プロジェクト テンプレートで指定されているプロパティ値とは異なるプロパティ値を必要とするために、プロパティを変更する。

- 異なるプロパティ値を指定する、**新しいプロジェクト** ダイアログ ボックス。

- プロジェクトのプロパティ ページで異なるプロパティ値を指定する。

> [!TIP]
> MSBuild がプロジェクトのビルドに使用するプロパティ値の最終的なセットを表示するには、ファイルを確認、プリプロセッサの出力をこのコマンドラインを使用して生成できます: **MSBuild 前処理/:** *preprocessor_output_filename*<sub>opt</sub> *project_filename*<sub>オプトイン</sub>

## <a name="resetting-properties"></a>プロパティのリセット

表示すると、**プロパティ ページ**プロジェクトおよびプロジェクト ノードのダイアログ ボックスがオンに**ソリューション エクスプ ローラー**、多くのプロパティを選択できます**親またはプロジェクトから継承既定値**値を変更または別の方法です。

表示すると、**プロパティ ページ**プロジェクトとファイルのダイアログ ボックスがオンに**ソリューション エクスプ ローラー**、多くのプロパティを選択できます**親またはプロジェクトの既定値から継承**値を変更または別の方法です。 ただし、プロジェクトの既定値とは異なるプロパティ値を持つファイルがプロジェクトに数多く含まれている場合、プロジェクトのビルドにかかる時間が長くなります。

> [!TIP]
> 更新する、**プロパティ ページ** ダイアログ ボックス、最新の選択を表示するよう選択**適用**です。

プロジェクトの既定値の大部分は、システム (プラットフォーム) の既定値です。 いくつかのプロジェクトの既定のプロパティを更新する場合に適用されるスタイル シートから派生して、**プロジェクトの既定値**のセクション、**全般**プロジェクトのプロパティ ページを構成します。 詳細については、次を参照してください。 [[全般] プロパティ ページ (プロジェクト)](../ide/general-property-page-project.md)です。

## <a name="specifying-user-defined-values"></a>ユーザー定義の値の指定

特定のプロパティに対して値を定義する必要があります。 ユーザー定義の値には、1 つ以上の英数字またはプロジェクト ファイル マクロ名を含めることができます。 これらのプロパティの一部には、ユーザー定義の値を 1 つしか受け取ることができないものもありますが、その他のプロパティはセミコロンで区切られた複数の値の一覧を受け取ることができます。

プロパティに対してユーザー定義の値 (プロパティが複数のユーザー定義の値を受け取ることができる場合は値の一覧) を指定するには、プロパティ名の右側の列で、次の操作のいずれかを実行します。

- 値または値の一覧を入力します。

- ドロップダウン矢印を選択します。 場合**編集**があることを選択し、テキスト ボックスに入力値または値の一覧です。 別の方法で一覧を指定するには、テキスト ボックス内で各値を別の行に入力します。 プロパティ ページに、セミコロンで区切られた値が表示されます。

   プロジェクト ファイル マクロを値としてを挿入するには、選択**マクロ**しマクロ名をダブルクリックします。

- ドロップダウン矢印を選択します。 場合**参照**があることを選択し、1 つまたは複数の値を選択します。

複数値プロパティの**親またはプロジェクトの既定値から継承**オプションは、プロパティ名の右側に列のドロップダウン矢印をクリックして、選択すると、使用可能な**編集**です。 既定では、このオプションはオンになっています。

プロパティ ページには、別のレベルから継承する複数値プロパティの、現在のレベルでの設定のみが表示される点に注意してください。 たとえば、ファイルが選択されて**ソリューション エクスプ ローラー** C/C++ を選択して**プリプロセッサの定義**プロパティ、ファイル レベルの定義が表示されますが、プロジェクト レベルの定義を継承表示されません。 現在のレベルと継承した値を表示、プロパティ名の右側に列のドロップダウン矢印を選択し、を**編集**です。 使用する場合、 [Visual C プロジェクト モデル](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.vcprojectengine)、この動作がファイルとプロジェクトのオブジェクトに対して有効にします。 つまり、ファイル レベルのプロパティの値を照会しても、プロジェクト レベルの同じプロパティの値は取得されません。 プロジェクト レベルのプロパティの値は、明示的に取得する必要があります。 また、プロパティの継承された値の一部はスタイル シートに由来する場合があり、これはプログラムによってアクセスすることはできません。

## <a name="in-this-section"></a>このセクションの内容

[詳細、マニフェスト ツールは、構成プロパティ、\<プロジェクト名 > プロパティ ページ ダイアログ ボックス](../ide/advanced-manifest-tool.md)

[[コマンド ライン] プロパティ ページ](../ide/command-line-property-pages.md)

[[カスタム ビルド ステップ] プロパティ ページ: 全般](../ide/custom-build-step-property-page-general.md)

[参照の追加](../ide/adding-references-in-visual-cpp-projects.md)

[[全般] プロパティ ページ (ファイル)](../ide/general-property-page-file.md)

[[全般] プロパティ ページ (プロジェクト)](../ide/general-property-page-project.md)

[一般に、マニフェスト ツール、構成プロパティ、\<プロジェクト名 > プロパティ ページ ダイアログ ボックス](../ide/general-manifest-tool-configuration-properties.md)

[[HLSL] プロパティ ページ](../ide/hlsl-property-pages.md)

[[詳細] ([HLSL] プロパティ ページ)](../ide/hlsl-property-pages-advanced.md)

[[全般] ([HLSL] プロパティ ページ)](../ide/hlsl-property-pages-general.md)

[[HLSL] プロパティ ページ: 出力ファイル](../ide/hlsl-property-pages-output-files.md)

[入力と出力、ツール、構成プロパティをマニフェスト\<プロジェクト名 > プロパティ ページ ダイアログ ボックス](../ide/input-and-output-manifest-tool.md)

[COM、マニフェスト ツールは、[構成プロパティを分離\<プロジェクト名 > プロパティ ページ] ダイアログ ボックス](../ide/isolated-com-manifest-tool.md)

[[リンカー] プロパティ ページ](../ide/linker-property-pages.md)

[[マネージ リソース] プロパティ ページ](../ide/managed-resources-property-page.md)

[[マニフェスト ツール] プロパティ ページ](../ide/manifest-tool-property-pages.md)

[[MIDL] プロパティ ページ](../ide/midl-property-pages.md)

[[詳細] ([MIDL] プロパティ ページ)](../ide/midl-property-pages-advanced.md)

[[全般] ([MIDL] プロパティ ページ)](../ide/midl-property-pages-general.md)

[[出力] ([MIDL] プロパティ ページ)](../ide/midl-property-pages-output.md)

[NMake プロパティ ページ](../ide/nmake-property-page.md)

[[リソース] プロパティ ページ](../ide/resources-property-pages.md)

[[VC++ ディレクトリ] プロパティ ページ](../ide/vcpp-directories-property-page.md)

[[Web 参照] プロパティ ページ](../ide/web-references-property-page.md)

[[XML データ ジェネレーター ツール] プロパティ ページ](../ide/xml-data-generator-tool-property-page.md)

[[XML ドキュメント ジェネレーター] プロパティ ページ](../ide/xml-document-generator-tool-property-pages.md)

## <a name="see-also"></a>関連項目

[方法 : プロジェクトの依存関係を作成および削除する](/visualstudio/ide/how-to-create-and-remove-project-dependencies)  
[方法 : 構成を作成および編集する](/visualstudio/ide/how-to-create-and-edit-configurations)  
