---
title: Visual Studio の C++ プロジェクトの MSBuild リファレンス
ms.date: 12/08/2018
helpviewer_keywords:
- MSBuild reference [C++]
ms.openlocfilehash: 96987a252d12f718025dd55deecad5c6bac26872
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336209"
---
# <a name="msbuild-reference-for-c-projects"></a>C++ プロジェクトの MSBuild リファレンス

MSBuild は、C++ プロジェクトを含む Visual Studio のすべてのプロジェクトのネイティブ ビルド システムです。 Visual Studio 統合開発環境 (IDE) でプロジェクトをビルドすると、msbuild.exe ツールが起動され、.vcxproj プロジェクト ファイル、およびさまざまな .targets ファイルと .props ファイルが使用されます。 一般に、プロジェクトのプロパティを設定し、MSBuild を呼び出すには、Visual Studio IDE を使用することを強くお勧めします。 プロジェクト ファイルを手動で編集すると、正しく行われなかった場合に深刻な問題が発生する可能性があります。

何らかの理由でコマンド ラインから MSBuild を直接使用する場合は、[コマンド ラインから MSBuild を使用するを](../msbuild-visual-cpp.md)参照してください。 MSBuild 全般の詳細については、Visual Studio のドキュメントの[「MSBuild」](/visualstudio/msbuild/msbuild)を参照してください。

## <a name="in-this-section"></a>このセクションの内容

[C++ プロジェクトの MSBuild の内部](msbuild-visual-cpp-overview.md)<br/>
プロパティとターゲットの格納方法と使用方法に関する情報。

[ビルドのコマンドとプロパティの共通マクロ](common-macros-for-build-commands-and-properties.md)<br/>
パスや製品バージョンなどのプロパティを定義するために使用できるマクロ (コンパイル時定数) について説明します。

[C++ プロジェクト用に作成されたファイルの種類](file-types-created-for-visual-cpp-projects.md)<br/>
さまざまな種類のプロジェクトに対して Visual Studio によって作成されるさまざまな種類のファイルについて説明します。

[Visual Studio C++ プロジェクト テンプレート](visual-cpp-project-types.md)<br>
C++ で使用できる MSBuild ベースのプロジェクトの種類について説明します。

[C++ 新しい項目テンプレート](using-visual-cpp-add-new-item-templates.md)<br>
Visual Studio プロジェクトに追加できるソース ファイルおよびその他の項目について説明します。

[プリコンパイル済みヘッダー ファイル](../creating-precompiled-header-files.md)プリコンパイル済みヘッダー ファイルの使用方法と、ビルド時間を短縮するための独自のカスタム プリコンパイル済みコードの作成方法。

[Visual Studio プロジェクト プロパティリファレンス](property-pages-visual-cpp.md)<br/>
Visual Studio IDE で設定されているプロジェクト プロパティのリファレンス ドキュメント。

## <a name="see-also"></a>関連項目

[C/C++ ビルドのリファレンス](c-cpp-building-reference.md)
