---
title: CLR をターゲットにした C++ プログラムのコンパイル | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- command-line applications [C++], managed code
- compiling programs [C++]
- Visual C++, managed code
- managed code [C++]
ms.assetid: 339f89df-a5d2-4040-831a-ddbe25b5dce4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2a7bcb0eead62730f0b70b0b1df64e5ed08f1f0
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "33336096"
---
# <a name="walkthrough-compiling-a-c-program-that-targets-the-clr-in-visual-studio"></a>チュートリアル: Visual Studio で CLR をターゲットにした C++ プログラムのコンパイル
.NET クラスを使用する Visual C++ プログラムを作成し、Visual Studio 開発環境を使用してそれをコンパイルすることができます。  
  
 この手順では、独自の Visual C++ プログラムを入力するか、いずれかのサンプル プログラムを使用できます。 この手順で使用するサンプル プログラムでは、textfile.txt という名前のテキスト ファイルを作成し、プロジェクト ディレクトリに保存します。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 これらのトピックは、C++ 言語の基本を理解していることを前提としています。  
  
### <a name="to-create-a-new-project-in-visual-studio-and-add-a-new-source-file"></a>Visual Studio で新しいプロジェクトを作成して新しいソース ファイルを追加するには  
  
1.  新しいプロジェクトを作成します。 **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。  
  
2.  Visual C++ プロジェクトの種類から、**[CLR]**、**[CLR 空プロジェクト]** の順にクリックします。  
  
3.  プロジェクト名を入力します。  
  
     既定では、プロジェクトを含むソリューションは新しいプロジェクトと同じ名前になりますが、別の名前を入力してもかまいません。 必要に応じて、プロジェクトの場所として別の場所を入力することもできます。  
  
     **[OK]** をクリックして、新しいプロジェクトを作成します。  
  
4.  ソリューション エクスプローラーが表示されていない場合は、**[表示]** メニューの **[ソリューション エクスプローラー]** をクリックします。  
  
5.  プロジェクトに新しいソース ファイルを追加します。  
  
    -   ソリューション エクスプローラーで、**[ソース ファイル]** フォルダーを右クリックし、**[追加]** をポイントして、**[新しい項目]** をクリックします。  
  
    -   **[C++ ファイル (.cpp)]** をクリックしてファイル名を入力し、**[追加]** をクリックします。  
  
     ソリューション エクスプローラーの**ソース ファイル** フォルダーに **.cpp** ファイルが表示されます。また、タブ付きウィンドウが表示され、ここでそのファイル内に含めるコードを入力します。  
  
6.  Visual Studio で新しく作成されたタブをクリックして、有効な Visual C++ プログラムを入力するか、サンプル プログラムのいずれかをコピーして貼り付けます。  
  
     たとえば、(プログラミング ガイドの**ファイル処理と I/O** ノード内の) 「[方法: テキスト ファイルを記述する (C++/CLI)](../dotnet/how-to-write-a-text-file-cpp-cli.md)」サンプル プログラムを使用できます。  
  
     サンプル プログラムを使用する場合は、.NET オブジェクトを作成するときに、`new` の代わりに `gcnew`キーワードを使用することと、`gcnew` がポインター (`*`) ではなくハンドル (`^`) を返すことに注意してください。  
  
     `StreamWriter^ sw = gcnew StreamWriter(fileName);`  
  
     新しい Visual C++ 構文の詳細については、「[ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)」を参照してください。  
  
7.  **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。  
  
     **[出力]** ウィンドウに、ビルド ログの場所やビルドの状態を示すメッセージなど、コンパイルの進行状況に関する情報が表示されます。  
  
     ビルドを行わずに、プログラムを変更して実行する場合、ダイアログ ボックスにプロジェクトが有効期限切れであることが示される場合があります。 Visual Studio がアプリケーションをビルドするたびに入力を求めるのではなく、常にファイルの現在のバージョンを使用するようにする場合は、このダイアログでチェック ボックスを選択してから **[OK]** をクリックします。  
  
8.  **[デバッグ]** メニューの **[デバッグなしで開始]** をクリックします。  
  
9. サンプル プログラムを使用した場合は、プログラムを実行するときに、テキスト ファイルが作成されたことを示すコマンド ウィンドウが表示されます。 任意のキーを押して、コマンド ウィンドウを閉じます。  
  
     これで **textfile.txt** テキスト ファイルがプロジェクトに配置されました。 このファイルはメモ帳を使用して開くことができます。  
  
    > [!NOTE]
    >  空の CLR プロジェクト テンプレートを選択すると、**/clr** コンパイラ オプションが自動的に設定されます。 これを確認するには、**ソリューション エクスプローラー**でプロジェクトを右クリックして、**[プロパティ]** をクリックしてから、**[構成プロパティ]** の **[全般]** ノードで **[共通言語ランタイム サポート]** オプションを確認します。  
  
## <a name="whats-next"></a>次の内容  
 **前へ:** [チュートリアル: コマンド ラインでのネイティブ C++ プログラムのコンパイル](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md) &#124; **次へ:** [チュートリアル: コマンド ラインでの C プログラムのコンパイル](../build/walkthrough-compile-a-c-program-on-the-command-line.md)  
  
## <a name="see-also"></a>参照  
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)