---
description: '詳細情報: コマンド ラインでの MSBuild - C++'
title: コマンド ラインでの MSBuild - C++
ms.date: 12/12/2018
helpviewer_keywords:
- MSBuild
ms.assetid: 7a1be7ff-0312-4669-adf2-5f5bf507d560
ms.openlocfilehash: 9d78c50b398b0ad97cfd75727fdb4219677c546b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179851"
---
# <a name="msbuild-on-the-command-line---c"></a>コマンド ラインでの MSBuild - C++

一般に、Visual Studio を使用してプロジェクトのプロパティを設定し、MSBuild システムを呼び出すことをお勧めします。 ただし、コマンド プロンプトから直接 **MSBuild** ツールを使用できます。 ビルド プロセスは、作成および編集できるプロジェクト ファイル (.vcxproj) の情報によって制御されます。 プロジェクト ファイルには、ビルドの段階、条件、およびイベントに基づくビルド オプションが指定されています。 さらに、0 個以上のコマンドラインの *options* 引数を指定できます。

> **msbuild.exe** [ *project_file* ] [ *options* ]

**/target** (または **/t**) および **/property** (または **/p**) コマンドライン オプションを使用して、プロジェクト ファイルで指定されている特定のプロパティとターゲットをオーバーライドします。

プロジェクト ファイルの重要な機能は、プロジェクトに適用される特定の操作を表す "*ターゲット*" と、その操作の実行に必要な入力および出力を指定することです。 プロジェクト ファイルでは 1 つ以上のターゲットを指定でき、既定のターゲットを含めることができます。

各ターゲットは、1 つ以上の "*タスク*" のシーケンスで構成されます。 各タスクは、実行可能なコマンドを 1 つ含む .NET Framework クラスによって表されます。 たとえば、[CL タスク](/visualstudio/msbuild/cl-task)には [cl.exe](reference/compiling-a-c-cpp-program.md) コマンドが含まれます。

"*タスク パラメーター*" はクラス タスクのプロパティであり、通常は実行可能なコマンドのコマンド ライン オプションを表します。 たとえば、`CL` タスクの `FavorSizeOrSpeed` パラメーターは、 **/Os** および **/Ot** の各コンパイラ オプションに対応しています。

追加のタスク パラメーターは、MSBuild インフラストラクチャをサポートします。 たとえば、`Sources` タスク パラメーターは、他のタスクで使用できる一連のタスクを指定します。 MSBuild タスクの詳細については、[タスク リファレンス](/visualstudio/msbuild/msbuild-task-reference)に関するページを参照してください。

ほとんどのタスクには入力と出力が必要です。これには、ファイル名、パス、文字列パラメーター、数値パラメーター、ブール値パラメーターなどがあります。 たとえば、一般的な入力は、コンパイルする .cpp ソース ファイルの名前です。 重要な入力パラメーターとして、ビルド構成とプラットフォームを指定する文字列があります。たとえば、"Debug\|Win32" のように指定します。 入力と出力は、`Item` 要素に含まれる 1 つ以上のユーザー定義の XML `ItemGroup` 要素で指定します。

プロジェクト ファイルには、ユーザー定義の "*プロパティ*" と `ItemDefinitionGroup` "*項目*" を指定することもできます。 プロパティと項目は、ビルドで変数として使用できる名前と値のペアを形成します。 ペアの名前コンポーネントによって "*マクロ*" が定義され、値コンポーネントによって "*マクロの値*" が宣言されます。 プロパティ マクロには $(*name*) 表記を使用してアクセスし、項目マクロには %(*name*) 表記を使用してアクセスします。

プロジェクト ファイル内の他の XML 要素では、マクロをテストし、条件に従ってマクロの値を設定したり、ビルドの実行を制御したりできます。 マクロ名とリテラル文字列を連結して、パスとファイル名などの構成要素を生成することもできます。 コマンド ラインで **/property** オプションを使用すると、プロジェクト プロパティが設定またはオーバーライドされます。 コマンド ラインで項目を参照することはできません。

MSBuild システムでは、あるターゲットを、条件に従って別のターゲットの前または後に実行できます。 また、ターゲットで使用されるファイルが出力されるファイルよりも新しいかどうかに基づいて、ターゲットをビルドすることもできます。

MSBuild の詳細については、以下を参照してください。

- [MSBuild](/visualstudio/msbuild/msbuild) MSBuild の概念の概要。

- [MSBuild リファレンス](/visualstudio/msbuild/msbuild-reference) MSBuild システムに関するリファレンス情報。

- [プロジェクト ファイル スキーマ リファレンス](/visualstudio/msbuild/msbuild-project-file-schema-reference) MSBuild XML スキーマ要素とその属性、親要素と子要素の一覧が掲載されています。 特に、[ItemGroup](/visualstudio/msbuild/itemgroup-element-msbuild)、[PropertyGroup](/visualstudio/msbuild/propertygroup-element-msbuild)、[Target](/visualstudio/msbuild/target-element-msbuild)、および [Task](/visualstudio/msbuild/task-element-msbuild) の各要素に注意してください。

- [コマンドライン リファレンス](/visualstudio/msbuild/msbuild-command-line-reference) msbuild.exe で使用できるコマンドライン引数とオプションが説明されています。

- [タスク リファレンス](/visualstudio/msbuild/msbuild-task-reference) MSBuild タスクが説明されています。 特に、Visual C++ に固有のタスクである [BscMake タスク](/visualstudio/msbuild/bscmake-task)、[CL タスク](/visualstudio/msbuild/cl-task)、[CPPClean タスク](/visualstudio/msbuild/cppclean-task)、[LIB タスク](/visualstudio/msbuild/lib-task)、[Link タスク](/visualstudio/msbuild/link-task)、[MIDL タスク](/visualstudio/msbuild/midl-task)、[MT タスク](/visualstudio/msbuild/mt-task)、[RC タスク](/visualstudio/msbuild/rc-task)、[SetEnv タスク](/visualstudio/msbuild/setenv-task)、[VCMessage タスク](/visualstudio/msbuild/vcmessage-task)に注意してください。

## <a name="in-this-section"></a>このセクションの内容

|用語|定義|
|----------|----------------|
|[チュートリアル: MSBuild を使用した C++ プロジェクトの作成](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)|**MSBuild** を使用して Visual Studio C++ プロジェクトを作成する方法を示します。|
|[方法: MSBuild プロジェクトでビルド イベントを使用する](how-to-use-build-events-in-msbuild-projects.md)|ビルドの特定の段階 (ビルドが始まる前、リンク ステップが始まる前、またはビルドが終了した後) で発生するアクションを指定する方法を示します。|
|[方法: MSBuild プロジェクトにカスタム ビルド ステップを追加する](how-to-add-a-custom-build-step-to-msbuild-projects.md)|ビルド シーケンスにユーザー定義の段階を追加する方法を示します。|
|[方法: MSBuild プロジェクトにカスタム ビルド ツールを追加する](how-to-add-custom-build-tools-to-msbuild-projects.md)|ビルド ツールを特定のファイルに関連付ける方法を示します。|
|[方法: カスタム ツールをプロジェクト プロパティに統合する](how-to-integrate-custom-tools-into-the-project-properties.md)|カスタム ツールのオプションをプロジェクトのプロパティに追加する方法を示します。|
|[方法: ターゲット フレームワークおよびプラットフォームのツールセットを変更する](how-to-modify-the-target-framework-and-platform-toolset.md)|複数のフレームワークまたはツールセットのプロジェクトをコンパイルする方法を示します。|

## <a name="see-also"></a>関連項目

[コマンド ラインから MSVC ツールセットを使用する](building-on-the-command-line.md)
