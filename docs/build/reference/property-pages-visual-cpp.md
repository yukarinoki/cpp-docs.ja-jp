---
description: '詳細情報: Windows C++ プロジェクトプロパティページリファレンス'
title: Windows C++ プロジェクトプロパティページリファレンス-Visual Studio
ms.date: 08/28/2019
helpviewer_keywords:
- project-file macro
- project properties [C++], default values
- user-defined values
- project properties [C++], setting
- macros, project-file
- property pages, project settings
- C++ projects, properties
- build macro
- user-defined macros
ms.assetid: 13ffe3ea-1bc3-4bee-be5e-053a8a99cce4
ms.openlocfilehash: 30e8f33f09242779529d368fbafc72ee66a0264f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225740"
---
# <a name="windows-c-project-property-page-reference"></a>Windows C++ プロジェクトプロパティページリファレンス

Visual Studio では、プロジェクトのプロパティページを使用して、コンパイラオプション、リンカーオプション、ファイルパス、およびその他のビルド設定を指定します。 使用できるプロパティおよびプロパティページは、プロジェクトの種類によって異なります。 たとえば、メイクファイルプロジェクトには、MFC または Win32 コンソールプロジェクトに存在しない NMake プロパティページがあります。 **プロパティページ** を開くには、メインメニューから [**プロジェクト** のプロパティ] を選択する  >  か、**ソリューションエクスプローラー** でプロジェクトノードを右クリックして [**プロパティ**] を選択します。 個々のファイルには、そのファイルに対してのみコンパイルオプションとビルドオプションを設定できるプロパティページもあります。 次の図は、MFC プロジェクトのプロパティページを示しています。

![C++ プロジェクトのプロパティページ](media/example-prop-page.png)

このセクションでは、プロパティページ自体のクイックリファレンスを示します。 プロパティページに表示されるオプションと設定は、独自のトピックで詳細に説明されており、プロパティページのトピックからリンクされています。 プロジェクトのプロパティの詳細については、「 [Visual Studio での C++ コンパイラとビルドプロパティの設定](../working-with-project-properties.md)」を参照してください。

Linux プロジェクトのプロパティページについては、「 [Linux C++ プロパティページリファレンス](../../linux/prop-pages-linux.md)」を参照してください。

## <a name="in-this-section"></a>このセクションの内容

- [[全般] プロパティページ (プロジェクト)](general-property-page-project.md)
- [[全般] プロパティ ページ (ファイル)](general-property-page-file.md)
- [[詳細設定] プロパティページ](advanced-property-page.md)
- [[VC + + ディレクトリ] プロパティページ](vcpp-directories-property-page.md)
- [リンカープロパティページ](linker-property-pages.md)
- [マニフェストツールのプロパティページ](manifest-tool-property-pages.md)
- [HLSL プロパティページ](hlsl-property-pages.md)
- [コマンドラインプロパティページ](command-line-property-pages.md)
- [[カスタムビルドステップ] プロパティページ: 全般](custom-build-step-property-page-general.md)
- [参照の追加](../adding-references-in-visual-cpp-projects.md)
- [[マネージリソース] プロパティページ](managed-resources-property-page.md)
- [MIDL プロパティページ](midl-property-pages.md)
- [[NMake] プロパティページ](nmake-property-page.md)
- [Resources プロパティページ](resources-property-pages.md)
- [[Web 参照] プロパティページ](web-references-property-page.md)
- [[XML データジェネレーターツール] プロパティページ](xml-data-generator-tool-property-page.md)
- [XML ドキュメントジェネレーターツールのプロパティページ](xml-document-generator-tool-property-pages.md)

## <a name="see-also"></a>関連項目

[方法: プロジェクトの依存関係を作成および削除する](/visualstudio/ide/how-to-create-and-remove-project-dependencies)<br/>
[方法: 構成を作成および編集する](/visualstudio/ide/how-to-create-and-edit-configurations)<br/>
[Linux C++ プロパティページリファレンス](../../linux/prop-pages-linux.md)
