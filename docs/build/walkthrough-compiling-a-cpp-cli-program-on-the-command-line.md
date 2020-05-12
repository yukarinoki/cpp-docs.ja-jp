---
title: 'チュートリアル: コマンド ラインでの C++/CLI プログラムのコンパイル'
ms.date: 04/23/2019
ms.assetid: cef41c88-faf9-439d-8423-25aa3f5674dd
ms.openlocfilehash: 8a5c5659367350a80725b365ef9c431bbec209d1
ms.sourcegitcommit: 18d3b1e9cdb4fc3a76f7a650c31994bdbd2bde64
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2019
ms.locfileid: "64877457"
---
# <a name="walkthrough-compiling-a-ccli-program-on-the-command-line"></a>チュートリアル: コマンド ラインでの C++/CLI プログラムのコンパイル

共通言語ランタイム (CLR) を対象とし、.NET Framework を使用する Visual C++ プログラムを作成して、コマンド ラインでビルドできます。 Visual C++ では C++/CLI プログラミング言語がサポートされます。このプログラミング言語には、.NET プログラミング モデルを対象とする追加の型と演算子があります。 C++/CLI 言語に関する一般的な情報については、「[C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)」を参照してください。

このチュートリアルでは、テキスト エディターを使って基本的な C++/CLI プログラムを作成し、コマンド ラインでコンパイルします。 (表示されているプログラムをタイプするのではなく、自分の C++/CLI プログラムを使用するか、別のヘルプ記事の C++/CLI コード サンプルを使用できます。 この手法は UI 要素が含まれていない小さなモジュールをビルドおよびテストするのに便利です)。

## <a name="prerequisites"></a>必須コンポーネント

C++ 言語の基本を理解していること。

## <a name="compiling-a-ccli-program"></a>C++/CLI プログラムのコンパイル

次の手順は、.NET Framework クラスを使用する C++/CLI コンソール アプリケーションをコンパイルする方法を示します。

C++/CLI のコンパイルを有効にするには、[/clr](reference/clr-common-language-runtime-compilation.md) コンパイラ オプションを使用する必要があります。 MSVC コンパイラは、MSIL コードまたは MSIL とネイティブ コードの混合を含む .exe ファイルを生成し、必要な .NET Framework ライブラリにリンクします。

### <a name="to-compile-a-ccli-application-on-the-command-line"></a>C++/CLI アプリケーションをコマンド ラインでコンパイルするには

1. **[開発者コマンド プロンプト]** ウィンドウを開きます。 具体的な手順については、「[開発者コマンド プロンプト ウィンドウを開くには](building-on-the-command-line.md#developer_command_prompt)」を参照してください。

   コンピューターのオペレーティング システムと構成によっては、コードを正常にコンパイルするために管理者の資格情報が必要な場合があります。 管理者としてコマンド プロンプト ウィンドウを実行するには、右クリックしてコマンド プロンプトのショートカット メニューを開き、 **[詳細]**  >  **[管理者として実行]** の順に選択します。

1. コマンド プロンプトで、「`notepad basicclr.cpp`」と入力します。

   ファイルを作成するかどうかを確認するメッセージが表示されたら、 **[はい]** を選択します。

1. メモ帳で、次の行を入力します。

   ```cpp
   int main()
   {
       System::Console::WriteLine("This is a C++/CLI program.");
   }
   ```

1. メニュー バーで、 **[ファイル]**  >  **[保存]** の順に選択します。

   <xref:System> 名前空間にある、.NET Framework クラス (<xref:System.Console>) を使用する Visual C++ ソース ファイルを作成しました。

1. コマンド プロンプトで、「`cl /clr basicclr.cpp`」と入力します。 cl.exe コンパイラによって、ソース コードは MSIL を含む .obj ファイルにコンパイルされ、リンカーが実行されて basicclr.exe という名前の実行可能プログラムが生成されます。

1. basicclr.exe プログラムを実行するには、コマンド プロンプトで「`basicclr`」と入力します。

   プログラムは、次のテキストを表示して終了します。

   ```Output
   This is a C++/CLI program.
   ```

## <a name="see-also"></a>関連項目

[C++ 言語リファレンス](../cpp/cpp-language-reference.md)<br/>
[プロジェクトおよびビルド システム](projects-and-build-systems-cpp.md)<br/>
[MSVC コンパイラ オプション](reference/compiler-options.md)
