---
title: '方法 : メイクファイル プロジェクトで IntelliSense を使用可能にする'
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCNMakeTool.IntelliSense
helpviewer_keywords:
- Makefile projects, IntelliSense
- IntelliSense, Makefile projects
ms.assetid: 9443f453-f18f-4f12-a9a1-ef9dbf8b188f
ms.openlocfilehash: 80a4696856fea46c7749cfeb120535dcdab86282
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434672"
---
# <a name="how-to-enable-intellisense-for-makefile-projects"></a>方法 : メイクファイル プロジェクトで IntelliSense を使用可能にする

特定のプロジェクト設定またはコンパイラ オプションが間違っていると、Visual C++ メイクファイル プロジェクト向けの IDE で IntelliSense が動作しません。 Visual Studio 開発環境でメイクファイル プロジェクトを開いたときに IntelliSense が動作するように、次の手順で Visual C++ メイクファイル プロジェクトを構成します。

### <a name="to-enable-intellisense-for-makefile-projects-in-the-ide"></a>IDE でメイクファイル プロジェクトに対して IntelliSense を有効にするには

1. **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)」を参照してください。

1. **[構成プロパティ]** ノードを展開します。

1. **[NMake]** プロパティ ページを選択し、**[IntelliSense]** のプロパティを適宜変更します。

   - **[プリプロセッサの定義]** プロパティでメイクファイル プロジェクトのプリプロセッサ シンボルを定義します。 詳細については、「[/D (プリプロセッサの定義)](../build/reference/d-preprocessor-definitions.md)」を参照してください。

   - メイクファイル プロジェクトのプリプロセッサ ディレクティブに渡されるファイル参照を解決する目的でコンパイラが検索するディレクトリの一覧を、**[インクルードの検索パス]** プロパティで指定します。 詳細については、「[/I (追加インクルード ディレクトリ)](../build/reference/i-additional-include-directories.md)」を参照してください。

         For projects that are built using CL.EXE from a Command Window, set the **INCLUDE** environment variable to specify directories that the compiler will search to resolve file references that are passed to preprocessor directives in your makefile project.

   - **[強制インクルード]** プロパティで、メイクファイル プロジェクトのビルド時に処理するヘッダー ファイルを指定します。 詳細については、「[/FI (強制インクルード ファイルの名前の指定)](../build/reference/fi-name-forced-include-file.md)」を参照してください。

   - プロジェクトの .NET アセンブリの参照を解決する目的でコンパイラが検索するディレクトリの一覧を **[アセンブリの検索パス]** プロパティで指定します。 詳細については、「[/AI (メタデータ ディレクトリの指定)](../build/reference/ai-specify-metadata-directories.md)」を参照してください。

   - **[アセンブリの強制使用]** プロパティで、メイクファイル プロジェクトのビルド時に処理する .NET アセンブリを指定します。 詳細については、「[/FU (強制 #using ファイルの名前の指定)](../build/reference/fu-name-forced-hash-using-file.md)」を参照してください。

   - C++ ファイルの解析時に IntelliSense によって使用される追加のコンパイラ スイッチを **[追加のオプション]** プロパティで指定します。

1. **[OK]** をクリックし、プロパティ ページを閉じます。

1. **[すべて保存]** コマンドを使用し、変更後のプロジェクト設定を保存します。

次回、Visual Studio 開発環境でメイクファイル プロジェクトを開くとき、**[ソリューションのクリーン]** コマンドを実行し、それからメイクファイル プロジェクトで **[ソリューションのビルド]** コマンドを実行します。 IntelliSense が IDE で正しく動作するはずです。

## <a name="see-also"></a>参照

[IntelliSense の使用](/visualstudio/ide/using-intellisense)<br>
[NMAKE リファレンス](../build/nmake-reference.md)<br>
[方法 : 既存のコードから C++ プロジェクトを作成する](../ide/how-to-create-a-cpp-project-from-existing-code.md)