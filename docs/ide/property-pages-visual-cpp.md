---
title: プロパティ ページ (Visual C++) | Microsoft Docs
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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33339710"
---
# <a name="property-pages-visual-c"></a>プロパティ ページ (Visual C++)

プロパティ ページを使用することで、Visual Studio プロジェクトの設定を指定できます。 Visual Studio プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開くには、**[プロジェクト]** メニューで **[プロパティ]** を選びます。

すべてのビルド構成に適用されるようにプロジェクト設定を指定することや、ビルド構成ごとに異なるプロジェクト プロパティを指定することができます。 たとえば、リリース構成の設定や、その他のデバッグ構成の設定を指定することができます。

すべての利用可能なページが、**[プロパティ ページ]** ダイアログ ボックスに表示されるとは限りません。 表示されるページは、プロジェクト内のファイルの種類によって異なります。

詳しくは、「[プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)」をご覧ください。

Windows 以外のプロジェクトについては、「[Linux C++ Property Page Reference](../linux/prop-pages-linux.md)<!-- or [C++ Cross Platform Property Page Reference](../linux/prop-pages-linux.md)-->」(Linux C++ プロパティ ページのリファレンス) をご覧ください。

## <a name="default-properties-vs-modified-properties"></a>既定のプロパティと変更されたプロパティの比較

**[新しいプロジェクト]** ダイアログ ボックスを使ってプロジェクトを作成すると、指定したプロジェクト テンプレートを使ってプロジェクトのプロパティが初期化されます。 そのため、テンプレート内のプロパティ値は、そのプロジェクトの種類の既定値と見なすことができます。 他のプロジェクトの種類では、プロパティの既定値が異なる場合があります。

プロジェクト プロパティ値は、変更されている場合は太字で表示されます。 プロジェクト プロパティは、次に示す理由によって変更される場合があります。

- アプリケーション ウィザードが、プロジェクト テンプレートで指定されているプロパティ値とは異なるプロパティ値を必要とするために、プロパティを変更する。

- **[新しいプロジェクト]** ダイアログ ボックスで異なるプロパティ値を指定する。

- プロジェクトのプロパティ ページで異なるプロパティ値を指定する。

> [!TIP]
> MSBuild がプロジェクトのビルドに使用する最終的なプロパティ値のセットを確認するには、プリプロセッサの出力ファイルを調べます。このファイルは、次のコマンド ラインを使用して生成できます。**MSBuild /preprocess:** <*プロセッサ出力ファイル名*><sub>opt</sub> <*プロジェクト ファイル名*><sub>opt</sub>

## <a name="resetting-properties"></a>プロパティのリセット

プロジェクトの **[プロパティ ページ]** ダイアログ ボックスが表示され、**ソリューション エクスプローラー**内でプロジェクト ノードが選択されている場合、多くのプロパティに対して、**[親またはプロジェクトの既定値から継承]** を選択するか、別の方法で値を変更することができます。

プロジェクトの **[プロパティ ページ]** ダイアログ ボックスが表示され、**ソリューション エクスプローラー**内でファイルが選択されている場合、多くのプロパティに対して、**[親またはプロジェクトの既定値から継承]** を選択するか、別の方法で値を変更することができます。 ただし、プロジェクトの既定値とは異なるプロパティ値を持つファイルがプロジェクトに数多く含まれている場合、プロジェクトのビルドにかかる時間が長くなります。

> [!TIP]
> 最新の選択状態が表示されるように **[プロパティ ページ]** ダイアログ ボックスを更新するには、**[適用]** を選びます。

プロジェクトの既定値の大部分は、システム (プラットフォーム) の既定値です。 プロジェクトの既定値の一部は、プロジェクトの **[全般]** 構成プロパティ ページの **[プロジェクトの既定値]** セクション内のプロパティが更新されたときに適用されるスタイル シートから派生しています。 詳しくは、「[[全般] プロパティ ページ (プロジェクト)](../ide/general-property-page-project.md)」をご覧ください。

## <a name="specifying-user-defined-values"></a>ユーザー定義の値の指定

特定のプロパティに対して値を定義する必要があります。 ユーザー定義の値には、1 つ以上の英数字またはプロジェクト ファイル マクロ名を含めることができます。 これらのプロパティの一部には、ユーザー定義の値を 1 つしか受け取ることができないものもありますが、その他のプロパティはセミコロンで区切られた複数の値の一覧を受け取ることができます。

プロパティに対してユーザー定義の値 (プロパティが複数のユーザー定義の値を受け取ることができる場合は値の一覧) を指定するには、プロパティ名の右側の列で、次の操作のいずれかを実行します。

- 値または値の一覧を入力します。

- ドロップダウン矢印を選びます。 **[編集]** を使用できる場合はこれをクリックし、テキスト ボックスに値または値の一覧を入力します。 別の方法で一覧を指定するには、テキスト ボックス内で各値を別の行に入力します。 プロパティ ページに、セミコロンで区切られた値が表示されます。

   プロジェクト ファイル マクロを値として挿入するには、**[マクロ]** を選び、次にマクロ名をダブルクリックします。

- ドロップダウン矢印を選びます。 **[参照]** を使用できる場合はこれを選び、1 つ以上の値を選択します。

複数値プロパティについては、プロパティ名の右側の列にあるドロップダウン矢印を選び、**[編集]** を選ぶと、**[親またはプロジェクトの既定値から継承]** オプションを使用できます。 既定では、このオプションはオンになっています。

プロパティ ページには、別のレベルから継承する複数値プロパティの、現在のレベルでの設定のみが表示される点に注意してください。 たとえば、**ソリューション エクスプローラー**でファイルが選択されている場合、C/C++ の **[プリプロセッサの定義]** プロパティを選択すると、ファイル レベルの定義は表示されますが、継承したプロジェクト レベルの定義は表示されません。 現在のレベルの値と継承した値を両方表示するには、プロパティ名の右側の列にあるドロップダウン矢印を選び、**[編集]** を選びます。 [Visual C++ プロジェクト モデル](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.vcprojectengine)を使用する場合、この動作はファイルおよびプロジェクト上のオブジェクトにも有効です。 つまり、ファイル レベルのプロパティの値を照会しても、プロジェクト レベルの同じプロパティの値は取得されません。 プロジェクト レベルのプロパティの値は、明示的に取得する必要があります。 また、プロパティの継承された値の一部はスタイル シートに由来する場合があり、これはプログラムによってアクセスすることはできません。

## <a name="in-this-section"></a>このセクションの内容

[[詳細] ([\<プロジェクト名> プロパティ ページ] ダイアログ ボックス - [構成プロパティ] - [マニフェスト ツール])](../ide/advanced-manifest-tool.md)

[[コマンド ライン] プロパティ ページ](../ide/command-line-property-pages.md)

[[カスタム ビルド ステップ] プロパティ ページ: 全般](../ide/custom-build-step-property-page-general.md)

[参照の追加](../ide/adding-references-in-visual-cpp-projects.md)

[[全般] プロパティ ページ (ファイル)](../ide/general-property-page-file.md)

[[全般] プロパティ ページ (プロジェクト)](../ide/general-property-page-project.md)

[[全般] ([\<プロジェクト名> プロパティ ページ] ダイアログ ボックス - [構成プロパティ] - [マニフェスト ツール])](../ide/general-manifest-tool-configuration-properties.md)

[[HLSL] プロパティ ページ](../ide/hlsl-property-pages.md)

[[詳細] ([HLSL] プロパティ ページ)](../ide/hlsl-property-pages-advanced.md)

[[全般] ([HLSL] プロパティ ページ)](../ide/hlsl-property-pages-general.md)

[[HLSL] プロパティ ページ: 出力ファイル](../ide/hlsl-property-pages-output-files.md)

[[入力と出力] ([\<プロジェクト名> プロパティ ページ] ダイアログ ボックス - [構成プロパティ] - [マニフェスト ツール])](../ide/input-and-output-manifest-tool.md)

[[分離された COM] ([\<プロジェクト名> プロパティ ページ] ダイアログ ボックス - [構成プロパティ] - [マニフェスト ツール])](../ide/isolated-com-manifest-tool.md)

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
