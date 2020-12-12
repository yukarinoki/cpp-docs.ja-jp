---
description: 詳細については、「C++ プロジェクトの MSBuild リファレンス」を参照してください。
title: Visual Studio での C++ プロジェクトの MSBuild リファレンス
ms.date: 12/08/2018
helpviewer_keywords:
- MSBuild reference [C++]
ms.openlocfilehash: 898757c8b7f1427c36e68a7227ec145abab8d078
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190615"
---
# <a name="msbuild-reference-for-c-projects"></a>C++ プロジェクトの MSBuild リファレンス

MSBuild は、Visual Studio のすべてのプロジェクト (C++ プロジェクトを含む) のネイティブビルドシステムです。 Visual Studio 統合開発環境 (IDE: integrated development environment) でプロジェクトをビルドすると、msbuild.exe ツールが呼び出されます。これにより、.vcxproj プロジェクトファイルとさまざまな .targets ファイルと props ファイルが使用されます。 一般に、Visual Studio IDE を使用してプロジェクトのプロパティを設定し、MSBuild を呼び出すことを強くお勧めします。 プロジェクトファイルを手動で編集すると、正常に実行されなかった場合に重大な問題が発生する可能性があります。

何らかの理由でコマンドラインから MSBuild を直接使用する必要がある場合は、「 [コマンドラインから msbuild を使用](../msbuild-visual-cpp.md)する」を参照してください。 MSBuild 全般の詳細については、Visual Studio ドキュメントの「 [msbuild](/visualstudio/msbuild/msbuild) 」を参照してください。

## <a name="in-this-section"></a>このセクションの内容

[C++ プロジェクトの MSBuild の内部](msbuild-visual-cpp-overview.md)<br/>
プロパティとターゲットを格納および使用する方法について説明します。

[ビルドのコマンドとプロパティの共通マクロ](common-macros-for-build-commands-and-properties.md)<br/>
パスや製品バージョンなどのプロパティを定義するために使用できるマクロ (コンパイル時定数) について説明します。

[C++ プロジェクト用に作成されたファイルの種類](file-types-created-for-visual-cpp-projects.md)<br/>
さまざまな種類のプロジェクトに対して Visual Studio によって作成されるさまざまな種類のファイルについて説明します。

[Visual Studio C++ プロジェクトテンプレート](visual-cpp-project-types.md)<br>
C++ で使用できる MSBuild ベースのプロジェクトの種類について説明します。

[C++ 新しい項目テンプレート](using-visual-cpp-add-new-item-templates.md)<br>
Visual Studio プロジェクトに追加できるソースファイルとその他の項目について説明します。

[プリコンパイル済みヘッダーファイル](../creating-precompiled-header-files.md) プリコンパイル済みヘッダーファイルの使用方法と、独自のカスタムプリコンパイル済みコードを作成してビルド時間を短縮する方法について説明します。

[Visual Studio プロジェクトのプロパティリファレンス](property-pages-visual-cpp.md)<br/>
Visual Studio IDE で設定されているプロジェクトプロパティに関するリファレンスドキュメントです。

## <a name="see-also"></a>関連項目

[C/C++ ビルドのリファレンス](c-cpp-building-reference.md)
