---
title: ビルドのカスタマイズのトラブルシューティング | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- build events [C++], troubleshooting
- builds [C++], build events
- troubleshooting [C++], builds
- build steps [C++], troubleshooting
- events [C++], build
- builds [C++], troubleshooting
- custom build steps [C++], troubleshooting
ms.assetid: e4ceb177-fbee-4ed3-a7d7-80f0d78c1d07
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2821c851c5b4498250a78f33eb111dd5f20ae272
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43895150"
---
# <a name="troubleshooting-build-customizations"></a>ビルドのカスタマイズのトラブルシューティング

カスタム ビルドのステップやイベントが予想どおりに動作しない場合、問題を理解する目的でいくつかのことを試すことができます。

- カスタム ビルド ステップで生成されるファイルが出力として宣言しているファイルに一致することを確認してください。

- 他のビルド ステップ (カスタムまたはカスタム以外) の入力か依存関係であるファイルがカスタム ビルド ステップによって生成されない場合、そのようなファイルがプロジェクトに追加されていることを確認してください。 また、そのようなファイルを利用するツールがカスタム ビルド ステップの後に実行されることを確認してください。

- カスタム ビルド ステップで実際に行われていることを表示するには、最初のコマンドとして `@echo on` を追加します。 ビルド イベントとビルド ステップは一時的な .bat ファイルに置かれ、プロジェクトがビルドされるときに実行されます。 そのため、ビルド イベント コマンドまたはビルド ステップ コマンドにエラー チェックを追加できます。

- 中間ファイル ディレクトリのビルド ログを調べ、実際に実行された内容を確認します。 ビルド ログのパスと名前は **MSBuild** マクロ式の **$(IntDir)\\$(MSBuildProjectName).log** によって表されます。

- ビルド ログに既定以上の量の情報が収集されるようにプロジェクト設定を変更します。 **[ツール]** メニューの **[オプション]** をクリックします。 **[オプション]** ダイアログ ボックスで、**[プロジェクトおよびソリューション]** ノードをクリックし、**[ビルド/実行]** ノードをクリックします。 次に、**[MSBuild プロジェクト ビルド ログ ファイルの詳細]** ボックスで **[詳細]** をクリックします。

- 使用しているファイル名またはディレクトリ マクロの値を確認します。 マクロは個別にエコーできます。あるいは、カスタム ビルド ステップの始まりに `copy %0 command.bat` を追加できますが、その場合、カスタム ビルド ステップのコマンドが command.bat にコピーされます。その際、すべてのマクロが展開されます。

- カスタムのビルド ステップとビルド イベント イベントを個別に実行し、その動作を確認します。

## <a name="see-also"></a>参照

[カスタム ビルド ステップとビルド イベントについて](../ide/understanding-custom-build-steps-and-build-events.md)