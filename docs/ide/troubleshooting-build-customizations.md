---
title: カスタマイズのビルドのトラブルシューティング |Microsoft ドキュメント
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
ms.openlocfilehash: d48e9f7bdcbf422a25fb0bdb40411e6c662fadc2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-build-customizations"></a>ビルドのカスタマイズのトラブルシューティング
カスタム ビルド ステップまたはイベントが期待どおりに動作していない場合、は、問題の原因を調べるために実行を行うことがいくつかの方法があります。  
  
-   カスタム ビルド ステップ生成ファイルが出力として宣言するファイルと一致することを確認してください。  
  
-   入力となるすべてのファイルを生成する、カスタム ビルド ステップ、またはその他の依存関係はビルド ステップ (カスタムまたはそれ以外の場合)、それらのファイルがプロジェクトに追加されたことを確認します。 カスタム ビルド ステップ後にそれらのファイルを使用するツールを実行するかどうかを確認します。  
  
-   カスタム ビルド ステップが実際に何を表示、追加`@echo on`最初のコマンドとして。 ビルド手順とビルド イベントに一時的な .bat ファイルに格納され、実行、プロジェクトのビルド時にします。 そのため、ビルド イベントの確認エラーを追加したり、ビルド ステップのコマンド。  
  
-   実際に実行される内容を表示する中間ファイル ディレクトリにあるビルド ログを調べます。 ビルド ログの名前とパスで表される、 **MSBuild**マクロ式 **$ (intdir)\\$(MSBuildProjectName) .log**です。  
  
-   複数の既定のビルド ログに情報量を収集するプロジェクトの設定を変更します。 **[ツール]** メニューの **[オプション]** をクリックします。 **オプション**ダイアログ ボックスで、をクリックして、**プロジェクトおよびソリューション**ノードをクリックして、**ビルドおよび実行する**ノード。 次に、 **MSBuild プロジェクト ビルド ログ ファイルの詳細**ボックスで、クリックして**Detailed**です。  
  
-   ファイルまたはディレクトリの名前のマクロを使用しているのいずれかの値を確認します。 マクロを個別にエコーできますしたり追加したり`copy %0 command.bat`カスタム ビルド ステップの開始日を展開されているすべてのマクロで command.bat にカスタム ビルド ステップのコマンドをコピーするは。  
  
-   カスタム ビルド ステップを実行し、その動作を確認するには、個別にイベントをビルドします。  
  
## <a name="see-also"></a>関連項目  
 [カスタム ビルド ステップとビルド イベントについて](../ide/understanding-custom-build-steps-and-build-events.md)