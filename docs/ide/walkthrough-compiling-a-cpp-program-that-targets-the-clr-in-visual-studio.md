---
title: CLR を対象とする C++ プログラムのコンパイル |Microsoft ドキュメント
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
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-compiling-a-c-program-that-targets-the-clr-in-visual-studio"></a>チュートリアル: Visual Studio で CLR をターゲットにした C++ プログラムのコンパイル
.NET クラスを使用し、Visual Studio 開発環境を使用してコンパイルする Visual C プログラムを作成することができます。  
  
 この手順は、独自の Visual C プログラムを入力または、サンプル プログラムのいずれかを使用できます。 この手順で使用するサンプル プログラムでは、textfile.txt という名前のテキスト ファイルを作成し、プロジェクト ディレクトリに保存します。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 これらのトピックでは、C++ 言語の基本を理解することを前提としています。  
  
### <a name="to-create-a-new-project-in-visual-studio-and-add-a-new-source-file"></a>Visual Studio で新しいプロジェクトを作成し、新しいソース ファイルを追加するには  
  
1.  新しいプロジェクトを作成します。 **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。  
  
2.  Visual C プロジェクトの種類をクリックして**CLR**、順にクリック**CLR 空プロジェクト**です。  
  
3.  プロジェクト名を入力します。  
  
     既定では、プロジェクトを含むソリューションが、新しいプロジェクトと同じ名前には、別の名前を入力することができます。 場合は、プロジェクトに別の場所を入力できます。  
  
     をクリックして**OK**新しいプロジェクトを作成します。  
  
4.  ソリューション エクスプ ローラーが表示されていない場合は、クリックして**ソリューション エクスプ ローラー**上、**ビュー**メニュー。  
  
5.  新しいソース ファイルをプロジェクトに追加します。  
  
    -   右クリックし、**ソース ファイル**フォルダー ソリューション エクスプローラで、指す**追加** をクリック**新しい項目の**します。  
  
    -   をクリックして**C++ ファイル (.cpp)** ファイル名を入力し、をクリックして**追加**です。  
  
     **.Cpp**ファイルに表示されます、**ソース ファイル**ソリューション エクスプ ローラーおよびタブ付きウィンドウ内のフォルダーは、コードを入力する場所が表示されますそのファイルに必要です。  
  
6.  Visual Studio で新しく作成された タブをクリックして、有効な Visual C プログラムを入力またはコピーして貼り付け、サンプル プログラムのいずれか。  
  
     たとえば、使用することができます、[する方法: テキスト ファイルを書き込む (C + + CLI)](../dotnet/how-to-write-a-text-file-cpp-cli.md)サンプル プログラム (で、**ファイルの処理と I/O**プログラミング ガイドのノード)。  
  
     サンプル プログラムを使用する場合は、使用することに注意してください。、`gcnew`キーワードの代わりに`new`、.NET オブジェクトを作成するときに`gcnew`ハンドルを返します (`^`) へのポインターではなく (`*`)。  
  
     `StreamWriter^ sw = gcnew StreamWriter(fileName);`  
  
     新しい Visual C 構文の詳細については、次を参照してください。[ランタイム プラットフォームのコンポーネント拡張](../windows/component-extensions-for-runtime-platforms.md)です。  
  
7.  **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。  
  
     **出力**ウィンドウは、ログの場所、ビルドとビルドの状態を示すメッセージなど、コンパイルの進行状況に関する情報を表示します。  
  
     変更して、ビルドを行わず、プログラムを実行する場合、ダイアログ ボックスが、プロジェクトが最新である可能性があります。 クリックする前に、このダイアログ ボックスのチェック ボックスをオン**OK**する場合は常に毎回の入力を求めるのではなく、ファイルの現在のバージョンを使用する Visual Studio でアプリケーションをビルドします。  
  
8.  **デバッグ** メニューのをクリックして**デバッグなしで開始**です。  
  
9. プログラムを実行するときに、サンプル プログラムを使用した場合は、テキスト ファイルが作成されたを示すコマンド ウィンドウが表示されます。 コマンド ウィンドウを閉じる任意のキーを押します。  
  
     **Textfile.txt**テキスト ファイルがプロジェクト ディレクトリにあるようになりました。 メモ帳を使用して、このファイルを開くことができます。  
  
    > [!NOTE]
    >  空の CLR を選択するプロジェクト テンプレートに自動的に設定されて、 **/clr**コンパイラ オプション。 これを確認するでプロジェクトを右クリックして**ソリューション エクスプ ローラー**をクリックすると、**プロパティ**、し、確認、**共通言語ランタイム サポート**オプション**一般的な**のノード**構成プロパティ**です。  
  
## <a name="whats-next"></a>次の内容  
 **前:** [チュートリアル: コマンドラインでネイティブ C++ プログラムのコンパイル](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md) &#124; **次:**[チュートリアル: コマンドラインで C プログラムをコンパイル](../build/walkthrough-compile-a-c-program-on-the-command-line.md)  
  
## <a name="see-also"></a>関連項目  
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)