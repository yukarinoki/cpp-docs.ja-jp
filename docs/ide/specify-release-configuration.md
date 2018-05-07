---
title: 既存のコードからプロジェクトを新しいリリースの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.importwiz.releasesettings
dev_langs:
- C++
ms.assetid: 3e2fc73c-bdbd-4790-b2bd-d31731f0cece
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4f3995b1a7227e4d2f0a531c86726b84e960d8ec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="specify-release-configuration-settings-create-new-project-from-existing-code-files-wizard"></a>[リリースの構成の設定] (既存コード ファイルからの新しいプロジェクトの作成ウィザード)
既存コード ファイルからの新しいプロジェクトの作成ウィザードのこのページを使用すると、リリース構成のプロジェクト設定を指定できます。  
  
## <a name="task-list"></a>タスク一覧  
 [方法 : 既存のコードから C++ プロジェクトを作成する](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## <a name="uielement-list"></a>UIElement の一覧  
 **デバッグ構成と同じ**  
 ウィザードがデバッグ構成のプロジェクト設定を同じリリース構成のプロジェクト設定を生成することを指定します。 このオプションは既定でオンにします。 このページ上の他のすべてのオプションがアクティブなこのボックスをオフにします。  
  
 **コマンド ライン ビルドします。**  
 新規プロジェクトをビルドするコマンドラインを指定します。 コンパイラとすべてのスイッチおよび新規プロジェクトのビルドに使用する引数の名前を入力します。 このオプションが有効になっているときに、**を使用して外部のビルド システム**オプションがオン、**プロジェクト設定の指定**ページ。  
  
 **コマンドラインを再構築します。**  
 新しいプロジェクトをリビルドするコマンドラインを指定します。 このオプションが有効になっているときに、**を使用して外部のビルド システム**オプションがオン、**プロジェクト設定の指定**ページ。  
  
 **クリーン コマンドライン**  
 新しいプロジェクトのビルド ツールによって生成されたサポート ファイルを削除するためのコマンドラインを指定します。 このオプションが有効になっているときに、**を使用して外部のビルド システム**オプションがオン、**プロジェクト設定の指定**ページ。  
  
 **出力 (デバッグ用)**  
 新しいプロジェクトのデバッグ構成の出力ファイルのディレクトリ パスを指定します。 このオプションが有効になっているときに、**を使用して外部のビルド システム**オプションがオン、**プロジェクト設定の指定**ページ。  
  
 **プリプロセッサの定義 (/D)**  
 新しいプロジェクトのプリプロセッサ シンボルを定義します。 詳細については、「 [/D (Preprocessor Definitions)](../build/reference/d-preprocessor-definitions.md)」を参照してください。  
  
 **検索パスを含める (/I)**  
 新しいプロジェクトのプリプロセッサ ディレクティブに渡されたファイル参照を解決するのには、コンパイラによって検索されるディレクトリの一覧に追加するディレクトリ パスを指定します。 詳細については、「[/I (追加インクルード ディレクトリ)](../build/reference/i-additional-include-directories.md)」を参照してください。  
  
 **強制インクルード ファイル (/FI)**  
 新しいプロジェクトをビルド時にヘッダー ファイルを指定します。 詳細については、「[/FI (強制インクルード ファイルの名前の指定)](../build/reference/fi-name-forced-include-file.md)」を参照してください。  
  
 **.NET アセンブリ検索パス (/AI)**  
 新しいプロジェクトのプリプロセッサ ディレクティブに渡される .NET アセンブリの参照を解決するのには、コンパイラによって検索されるディレクトリのパスを指定します。 詳細については、「[/AI (メタデータ ディレクトリの指定)](../build/reference/ai-specify-metadata-directories.md)」を参照してください。  
  
 **.NET アセンブリを使用して強制的に (/FU)**  
 新しいプロジェクトをビルド時に .NET アセンブリを指定します。 詳細については、「[/FU (強制 #using ファイルの名前の指定)](../build/reference/fu-name-forced-hash-using-file.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [[プロジェクト設定の指定] (既存コード ファイルからの新しいプロジェクトの作成ウィザード)](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)