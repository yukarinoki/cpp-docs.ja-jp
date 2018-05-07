---
title: メイクファイル プロジェクトの作成 |Microsoft ドキュメント
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
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="creating-a-makefile-project"></a>メイクファイル プロジェクトの作成

メイクファイルを使用してコマンドラインからビルドする既存のソース コード プロジェクトがある場合は、Visual Studio 開発環境は Visual Studio IDE 機能を最大限に活用できますをプロジェクトにいくつかの方法がします。 この記事では、IDE でコードをビルドする、既存のメイクファイルを使用している Visual Studio でメイクファイル プロジェクトを作成する方法について説明します。 また、使用することができます、**既存コード ファイルから新しいプロジェクトの作成**ソース コードからネイティブ MSBuild プロジェクトを作成するウィザード。 詳細については、「[方法 : 既存のコードから C++ プロジェクトを作成する](how-to-create-a-cpp-project-from-existing-code.md)」を参照してください。 Visual Studio 2017 以降、使用することも、**フォルダーを開く**場合ネイティブの Visual Studio プロジェクトと同様に、いくつかの既存のビルド システムを使用できる機能です。 詳細については、「[Open Folder projects in Visual C++ (Visual C++ の [フォルダーを開く] プロジェクト)](non-msbuild-projects.md)」をご覧ください。

Visual Studio を開いて、既存のメイクファイルを使用して、ソース コードをビルドを使用するのには、メイクファイル プロジェクト テンプレートを選択して最初新しいプロジェクトを作成するだけです。 ウィザードでは、コマンドと、メイクファイルを使用する環境を指定できます。 このプロジェクトを使用して、Visual Studio 開発環境でコードをビルドすることができますし、します。

既定では、メイクファイル プロジェクトが表示されませんファイル エクスプ ローラーでソリューション。 メイクファイル プロジェクトでは、ビルド構成には、プロジェクトのプロパティ ページに反映されますを指定します。

プロジェクトで指定した出力ファイルは、ビルド スクリプトの生成するファイルの名前には直接は影響しません。 メイクファイルはまだビルド プロセスを制御し、ビルド ターゲットを指定します。

## <a name="to-create-a-makefile-project"></a>メイクファイル プロジェクトを作成するには

1. ヘルプ トピックの指示に従って、 [Visual C のアプリケーション ウィザードでプロジェクトを作成する](../ide/creating-desktop-projects-by-using-application-wizards.md)です。

1. **新しいプロジェクト**] ダイアログ ボックスで、展開**Visual C** > **全般**し、[**メイクファイル プロジェクト**で、[テンプレート] ペインを開くには、プロジェクト ウィザード。

1. [アプリケーション設定](../ide/application-settings-makefile-project-wizard.md) ページで、コマンドの出力結果は次のクリーンアップ、およびデバッグ版および製品の情報を再構築のビルドを提供します。

1. をクリックして**完了**、ウィザードを終了しで新しく作成されたプロジェクトを開く**ソリューション エクスプ ローラー**です。

プロジェクトのプロパティは、プロパティ ページで表示および編集できます。 参照してください[Visual C プロジェクトのプロパティの設定](../ide/working-with-project-properties.md)については、プロパティ ページを表示します。

## <a name="see-also"></a>関連項目

[メイクファイル アプリケーション ウィザード](../ide/makefile-project-wizard.md)<br/>
[メイクファイルの特殊文字](../build/special-characters-in-a-makefile.md)<br/>
[メイクファイルの内容](../build/contents-of-a-makefile.md)<br/>
