---
title: '方法: メイクファイル プロジェクトの IntelliSense を有効にする |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCNMakeTool.IntelliSense
dev_langs:
- C++
helpviewer_keywords:
- Makefile projects, IntelliSense
- IntelliSense, Makefile projects
ms.assetid: 9443f453-f18f-4f12-a9a1-ef9dbf8b188f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9de79d56c6e8b6e496c0e7988ada07ed7595ea70
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enable-intellisense-for-makefile-projects"></a>方法 : メイクファイル プロジェクトで IntelliSense を使用可能にする
特定のプロジェクト設定、またはコンパイラ オプション、ときに、Visual C メイクファイル プロジェクトの場合は、IDE での操作に失敗する IntelliSense が正しく設定されていません。 メイクファイル プロジェクトを Visual Studio 開発環境で開いているときに IntelliSense が動作するように、Visual C メイクファイル プロジェクトを構成するのにこの手順を使用します。  
  
### <a name="to-enable-intellisense-for-makefile-projects-in-the-ide"></a>メイクファイル プロジェクトの場合、IDE での IntelliSense を有効にするには  
  
1.  開く、**プロパティ ページ** ダイアログ ボックス。 詳細については、「[のプロジェクト プロパティの操作](../ide/working-with-project-properties.md)です。  
  
2.  展開して、**構成プロパティ**ノード。  
  
3.  選択、 **NMake**プロパティ ページ、および のプロパティを変更**IntelliSense**に応じて。  
  
    -   設定、**プリプロセッサの定義**メイクファイル プロジェクトのすべてのプリプロセッサ シンボルを定義するプロパティです。 参照してください[/D (プリプロセッサの定義)](../build/reference/d-preprocessor-definitions.md)、詳細についてはします。  
  
    -   設定、**インクルード検索パス**メイクファイル プロジェクトのプリプロセッサ ディレクティブに渡されたファイル参照を解決するのには、コンパイラによって検索されるディレクトリの一覧を指定するプロパティです。 参照してください[/I (追加インクルード ディレクトリ)](../build/reference/i-additional-include-directories.md)、詳細についてはします。  
  
         CL を使用して構築されているプロジェクトの場合です。コマンド ウィンドウで、exe ファイルの設定、 **INCLUDE**環境変数をメイクファイル プロジェクトのプリプロセッサ ディレクティブに渡されたファイル参照を解決するのには、コンパイラによって検索されるディレクトリを指定します。  
  
    -   設定、**強制インクルード**メイクファイル プロジェクトのビルド時にヘッダーがプロセスにファイルを指定するプロパティです。 参照してください[/FI (強制含めるファイルの名前)](../build/reference/fi-name-forced-include-file.md)、詳細についてはします。  
  
    -   設定、**アセンブリ検索パス**プロパティをプロジェクト内の .NET アセンブリへの参照を解決するのには、コンパイラによって検索されるディレクトリの一覧を指定します。 参照してください[/AI (メタデータ ディレクトリの指定)](../build/reference/ai-specify-metadata-directories.md)、詳細についてはします。  
  
    -   設定、**アセンブリの強制使用**メイクファイル プロジェクトのビルド時に使用される .NET アセンブリを指定するプロパティです。 参照してください[/FU (Name Forced #using ファイルの using)](../build/reference/fu-name-forced-hash-using-file.md)、詳細についてはします。  
  
    -   設定、**追加オプション**プロパティを C++ ファイルを解析するときに Intellisense によって使用する追加のコンパイラ スイッチを指定します。  
  
4.  をクリックして**OK**プロパティ ページを閉じます。  
  
5.  使用して、**すべて保存**変更されたプロジェクトの設定を保存するコマンド。  
  
 次回開くメイクファイル プロジェクト、Visual Studio 開発環境で、実行、**ソリューションのクリーン**コマンドし、**ソリューションのビルド**メイクファイル プロジェクトのコマンド。 IntelliSense は、IDE で正しく動作する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [IntelliSense の使用](/visualstudio/ide/using-intellisense)   
 [NMAKE リファレンス](../build/nmake-reference.md)   
 [方法 : 既存のコードから C++ プロジェクトを作成する](../ide/how-to-create-a-cpp-project-from-existing-code.md)