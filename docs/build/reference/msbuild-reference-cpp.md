---
title: Visual Studio で C++ プロジェクトの MSBuild のリファレンス
ms.date: 12/08/2018
helpviewer_keywords:
- MSBuild reference [C++]
ms.openlocfilehash: 854dc0554c327f191b4b4b9694548cdb9983c5f8
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826888"
---
# <a name="msbuild-reference-for-c-projects"></a>C++ プロジェクトの MSBuild のリファレンス

MSBuild は、Visual studio で C++ プロジェクトを含むすべてのプロジェクトのネイティブ ビルド システムです。 Visual Studio 統合開発環境 (IDE) でプロジェクトをビルドする場合は、.vcxproj プロジェクト ファイル、およびさまざまな .targets および .props ファイルをさらに消費する msbuild.exe ツールを呼び出します。 一般に、Visual Studio IDE を使用して、プロジェクトのプロパティを設定し、MSBuild を呼び出すを強くお勧めします。 正しく行われていない場合のプロジェクト ファイルを手動で編集は重大な問題につながります。

直接コマンドラインから MSBuild を使用する何らかの理由は場合を参照してください。[コマンドラインから MSBuild を使用して](../msbuild-visual-cpp.md)します。 MSBuild の詳細については一般に、表示[MSBuild](/visualstudio/msbuild/msbuild) Visual Studio ドキュメント。

## <a name="in-this-section"></a>このセクションの内容

[C++ プロジェクトの MSBuild の内部](msbuild-visual-cpp-overview.md)<br/>
プロパティとターゲットが格納されているし、使用方法について説明します。

[ビルドのコマンドとプロパティの共通マクロ](common-macros-for-build-commands-and-properties.md)<br/>
パスとバージョンの製品などのプロパティを定義するのに使用できるマクロ (コンパイル時定数) について説明します。

[C++ プロジェクトに対して作成されるファイルの種類](file-types-created-for-visual-cpp-projects.md)<br/>
異なる種類のプロジェクト用 Visual Studio によって作成されるファイルのさまざまな種類について説明します。

[Visual Studio の C++ プロジェクト テンプレート](visual-cpp-project-types.md)<br>
C++ で利用可能な MSBuild ベースのプロジェクトの種類について説明します。

[C++ の新しい項目テンプレート](using-visual-cpp-add-new-item-templates.md)<br>
ソース ファイルと Visual Studio プロジェクトに追加できるその他の項目について説明します。

[プリコンパイル済みヘッダー ファイル](../creating-precompiled-header-files.md)プリコンパイル済みビルド時間を短縮するためのコードをプリコンパイル済みヘッダー ファイルと、独自のカスタムを作成する方法を使用する方法。

[Visual Studio プロジェクトのプロパティの参照](property-pages-visual-cpp.md)<br/>
Visual Studio IDE で設定されているプロジェクトのプロパティのリファレンス ドキュメント。

## <a name="see-also"></a>関連項目

[C/C++ ビルドのリファレンス](c-cpp-building-reference.md)