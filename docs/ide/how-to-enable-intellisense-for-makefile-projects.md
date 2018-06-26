---
title: '方法 : メイクファイル プロジェクトで IntelliSense を使用可能にする | Microsoft Docs'
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
ms.openlocfilehash: 4b9b11f04f1fe8d201d6d07ca5ed83f9ca7d991b
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705463"
---
# <a name="how-to-enable-intellisense-for-makefile-projects"></a>方法 : メイクファイル プロジェクトで IntelliSense を使用可能にする
特定のプロジェクト設定またはコンパイラ オプションが間違っていると、Visual C++ メイクファイル プロジェクト向けの IDE で IntelliSense が動作しません。 Visual Studio 開発環境でメイクファイル プロジェクトを開いたときに IntelliSense が動作するように、次の手順で Visual C++ メイクファイル プロジェクトを構成します。  
  
### <a name="to-enable-intellisense-for-makefile-projects-in-the-ide"></a>IDE でメイクファイル プロジェクトに対して IntelliSense を有効にするには  
  
1.  **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **[構成プロパティ]** ノードを展開します。  
  
3.  **[NMake]** プロパティ ページを選択し、**[IntelliSense]** のプロパティを適宜変更します。  
  
    -   **[プリプロセッサの定義]** プロパティでメイクファイル プロジェクトのプリプロセッサ シンボルを定義します。 詳細については、「[/D (プリプロセッサの定義)](../build/reference/d-preprocessor-definitions.md)」を参照してください。  
  
    -   メイクファイル プロジェクトのプリプロセッサ ディレクティブに渡されるファイル参照を解決する目的でコンパイラが検索するディレクトリの一覧を、**[インクルードの検索パス]** プロパティで指定します。 詳細については、「[/I (追加インクルード ディレクトリ)](../build/reference/i-additional-include-directories.md)」を参照してください。  
  
         コマンド ウィンドウから CL.EXE を利用してビルドするプロジェクトの場合、メイクファイル プロジェクトのプリプロセッサ ディレクティブに渡されるファイル参照を解決する目的でコンパイラが検索するディレクトリの一覧を、**INCLUDE** 環境変数で指定します。  
  
    -   **[強制インクルード]** プロパティで、メイクファイル プロジェクトのビルド時に処理するヘッダー ファイルを指定します。 詳細については、「[/FI (強制インクルード ファイルの名前の指定)](../build/reference/fi-name-forced-include-file.md)」を参照してください。  
  
    -   プロジェクトの .NET アセンブリの参照を解決する目的でコンパイラが検索するディレクトリの一覧を **[アセンブリの検索パス]** プロパティで指定します。 詳細については、「[/AI (メタデータ ディレクトリの指定)](../build/reference/ai-specify-metadata-directories.md)」を参照してください。  
  
    -   **[アセンブリの強制使用]** プロパティで、メイクファイル プロジェクトのビルド時に処理する .NET アセンブリを指定します。 詳細については、「[/FU (強制 #using ファイルの名前の指定)](../build/reference/fu-name-forced-hash-using-file.md)」を参照してください。  
  
    -   C++ ファイルの解析時に IntelliSense によって使用される追加のコンパイラ スイッチを **[追加のオプション]** プロパティで指定します。  
  
4.  **[OK]** をクリックし、プロパティ ページを閉じます。  
  
5.  **[すべて保存]** コマンドを使用し、変更後のプロジェクト設定を保存します。  
  
 次回、Visual Studio 開発環境でメイクファイル プロジェクトを開くとき、**[ソリューションのクリーン]** コマンドを実行し、それからメイクファイル プロジェクトで **[ソリューションのビルド]** コマンドを実行します。 IntelliSense が IDE で正しく動作するはずです。  
  
## <a name="see-also"></a>参照  
 [IntelliSense の使用](/visualstudio/ide/using-intellisense)   
 [NMAKE リファレンス](../build/nmake-reference.md)   
 [方法 : 既存のコードから C++ プロジェクトを作成する](../ide/how-to-create-a-cpp-project-from-existing-code.md)