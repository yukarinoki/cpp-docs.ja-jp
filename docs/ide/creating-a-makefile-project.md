---
title: メイクファイル プロジェクトの作成 | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.makefile.project
dev_langs:
- C++
helpviewer_keywords:
- Makefile projects, creating
- project files [C++], Makefile projects
ms.assetid: dd077af3-97a8-48fb-baaa-cf7e07ddef61
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dc854f96f1c41baf28a5af4ca1f253e47d9a8914
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "33336779"
---
# <a name="creating-a-makefile-project"></a>メイクファイル プロジェクトの作成

メイクファイルを使用してコマンド ラインからビルドした既存のソース コード プロジェクトがある場合、Visual Studio 開発環境には、Visual Studio IDE 機能を最大限に活用できるプロジェクトにするための方法がいくつかあります。 この記事では、Visual Studio でメイクファイル プロジェクトを作成する方法について説明します。ここでは、既存のメイクファイルを使用して IDE でコードをビルドします。 また、**[既存コード ファイルからの新しいプロジェクトの作成]** ウィザードを使用して、ソース コードからネイティブ MSBuild プロジェクトを作成することもできます。 詳細については、「[方法 : 既存のコードから C++ プロジェクトを作成する](how-to-create-a-cpp-project-from-existing-code.md)」を参照してください。 Visual Studio 2017 以降、ネイティブ Visual Studio プロジェクトであれば、いくつかの既存のビルド システムを使用できる **[フォルダーを開く]** 機能を使用することもできます。 詳細については、「[Open Folder projects in Visual C++ (Visual C++ の [フォルダーを開く] プロジェクト)](non-msbuild-projects.md)」をご覧ください。

Visual Studio を使用して、既存のメイクファイルを使用してソース コードを開いてビルドするには、まずメイクファイル プロジェクト テンプレートを選択して新しいプロジェクトを作成します。 ウィザードを使用すると、メイクファイルによって使用されるコマンドと環境を指定するのに役立ちます。 次に、このプロジェクトを使用して、Visual Studio 開発環境でコードをビルドできます。

既定では、ソリューション エクスプローラーにメイクファイル プロジェクトのファイルは表示されません。 メイクファイル プロジェクトで指定したビルド構成は、プロジェクトのプロパティ ページに反映されます。

プロジェクトで指定した出力ファイルは、ビルド スクリプトの生成するファイルの名前には直接は影響しません。 メイクファイルでは、引き続きビルド プロセスの制御とビルド ターゲットの指定を行います。

## <a name="to-create-a-makefile-project"></a>メイクファイル プロジェクトを作成するには

1. ヘルプ トピックの「[アプリケーション ウィザードを使用したデスクトップ プロジェクトの作成](../ide/creating-desktop-projects-by-using-application-wizards.md)」の手順に従います。

1. **[新しいプロジェクト]** ダイアログ ボックスで **[Visual C++]** > **[全般]** を展開し、[テンプレート] ウィンドウの **[メイクファイル プロジェクト]** を選択してプロジェクト ウィザードを開きます。

1. [[アプリケーションの設定]](../ide/application-settings-makefile-project-wizard.md) ページで、デバッグと製品ビルドに対してコマンド、出力、クリーンアップ、およびリビルドに関する情報を指定します。

1. **[完了]** をクリックしてウィザードを閉じ、**ソリューション エクスプローラー**で新しく作成したプロジェクトを開きます。

プロジェクトのプロパティは、プロパティ ページで表示および編集できます。 プロパティ ページの表示方法については、[Visual C++ プロジェクトのプロパティの設定](../ide/working-with-project-properties.md)に関するページを参照してください。

## <a name="see-also"></a>参照

[メイクファイル アプリケーション ウィザード](../ide/makefile-project-wizard.md)<br/>
[メイクファイルの特殊文字](../build/special-characters-in-a-makefile.md)<br/>
[メイクファイルの内容](../build/contents-of-a-makefile.md)<br/>
