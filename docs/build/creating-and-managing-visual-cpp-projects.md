---
title: Visual Studio プロジェクトの C++
ms.date: 12/12/2018
f1_keywords:
- vcprojects
- creatingmanagingVC
helpviewer_keywords:
- ATL projects, creating
- Visual C++ projects, creating
- projects [C++], creating
- Visual C++ projects
- ATL projects
ms.assetid: 11003cd8-9046-4630-a189-a32bf3b88047
ms.openlocfilehash: b5fb9ac87547578f101676d4cf424c7065155842
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826908"
---
# <a name="visual-studio-projects---c"></a>Visual Studio プロジェクトの C++

A *Visual Studio プロジェクト*は MSBuild のビルド システムに基づくプロジェクト。 MSBuild は Visual Studio のネイティブ ビルド システムですし、MFC または ATL ライブラリ、COM コンポーネント、およびその他の Windows 固有のプログラムを使用するデスクトップ アプリケーションと、UWP アプリを使用するシステムを構築する最適な一般にします。 MSBuild は Visual Studio と密接に連携しますが、コマンドラインから使用することもできます。 

## <a name="create-a-project"></a>プロジェクトを作成する

C++ プロジェクトを作成するには選択して**ファイル&#124;新規&#124;プロジェクト**、左側のウィンドウで、Visual C を選択し、します。 中央のウィンドウでプロジェクト テンプレートの一覧を参照してください。 

   ![プロジェクト テンプレート](../media/vs2017-new-project.png "Visual Studio 2017 の [新しいプロジェクト] ダイアログ")

Visual Studio に含まれているすべての既定プロジェクト テンプレートの詳細については、次を参照してください。 [Visual Studio で C++ プロジェクト テンプレート](reference/visual-cpp-project-types.md)します。 独自のプロジェクト テンプレートを作成することができます。 詳細については、「[方法 :プロジェクト テンプレートを作成](/visualstudio/ide/how-to-create-project-templates)です。

表示されますが、プロジェクトを作成した後、[ソリューション エクスプ ローラー](/visualstudio/ide/solutions-and-projects-in-visual-studio)ウィンドウ。

   ![ソリューション エクスプローラー](media/mathlibrary-solution-explorer-153.png)

新しいプロジェクトを作成するときにソリューション ファイル (.sln) も作成されます。 その他のプロジェクトをソリューションに追加するにを右クリックしてで**ソリューション エクスプ ローラー**します。 ソリューション ファイルは、複数の関連プロジェクトがあるが、もっと多くのことを行わない場合に、ビルドの依存関係を調整するために使用されます。 すべてのコンパイラ オプションは、プロジェクト レベルで設定されます。

## <a name="add-items"></a>項目を追加します。

プロジェクトを右クリックして、ソース コード ファイル、アイコン、またはその他の項目をプロジェクトに追加**ソリューション エクスプ ローラー**を選択して**追加 > 新規**または**追加 > 既存**します。

## <a name="add-third-party-libraries"></a>サード パーティ製のライブラリを追加します。

サードパーティ製のライブラリを追加するには、使用、 [vcpkg](../vcpkg.md)パッケージ マネージャー。 任意の Visual Studio プロジェクトから参照するときにそのライブラリへのパスを設定する Visual Studio の統合手順を実行します。 

## <a name="set-compiler-options-and-other-build-properties"></a>コンパイラ オプションとその他のビルド プロパティを設定します。

プロジェクトを右クリックし、プロジェクトのビルド設定を構成する**ソリューション エクスプ ローラー**選択**プロパティ**します。 詳細については、次を参照してください。 [Visual Studio での設定の C++ コンパイラとビルド プロパティ](working-with-project-properties.md)します。

## <a name="compile-and-run"></a>コンパイルし、実行

をコンパイルして新しいプロジェクトを実行するキーを押します**F5**  をクリックしてまたは、*デバッグ ドロップダウン*メイン ツールバーの緑色の矢印の付いたします。 *構成ドロップダウン*を実行するかどうかを選択、*デバッグ*または*リリース*ビルド (またはその他のいくつかのカスタム構成)。

エラーのない新しいプロジェクトをコンパイルします。 独自のコードを追加するときに、間違いが起こりやすいまたはと警告がトリガー場合によっては可能性があります。 エラーが原因で、ビルドが完了しません。警告は提供されません。 プロジェクトをビルドするときに、すべてのエラーと警告が出力ウィンドウと エラー一覧の両方には表示します。 

   ![出力ウィンドウおよびエラーの一覧](../media/vs2017-output-error-list.png)

[エラー一覧] でキーを押して**F1**でそのドキュメントのトピックに移動すると、強調表示されているエラー。

## <a name="in-this-section"></a>このセクションの内容

[C++ コンパイラを設定し、Visual Studio でのプロパティのビルド](working-with-project-properties.md)<br/>
プロパティ ページとプロパティ シートを使用して、プロジェクトの設定を指定する方法。

[参照ライブラリおよびビルド時にコンポーネント](adding-references-in-visual-cpp-projects.md)<br/>
プロジェクトにライブラリ、Dll、COM および .NET コンポーネントを含める方法です。
 
[プロジェクト出力ファイルを整理します。](how-to-organize-project-output-files-for-builds.md)<br/>
ビルド プロセスで作成した実行可能ファイルの場所をカスタマイズする方法。

[カスタム ビルド ステップとビルド イベント](understanding-custom-build-steps-and-build-events.md)<br/>
指定した時点で、ビルド プロセスを任意のコマンドを追加する方法。

[既存のコードからプロジェクトを作成する](how-to-create-a-cpp-project-from-existing-code.md)<br/>
ソース ファイルの緩やかなコレクションから新しい Visual Studio プロジェクトを作成する方法。

## <a name="see-also"></a>関連項目

[プロジェクトおよびビルド システム](projects-and-build-systems-cpp.md)<br>
