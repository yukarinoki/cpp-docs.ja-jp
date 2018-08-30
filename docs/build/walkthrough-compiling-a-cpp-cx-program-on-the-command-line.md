---
title: 'チュートリアル: をコンパイルする c++/cli コマンドラインで/CX プログラム |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 626f5544-69ed-4736-83a9-f11389b371b2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc4e6dbf3023256a6a0db556c02e08453bb1a730
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194276"
---
# <a name="walkthrough-compiling-a-ccx-program-on-the-command-line"></a>チュートリアル: コマンド ラインでの C++/CX プログラムのコンパイル
Windows ランタイムをターゲットにする Visual C++ プログラムを作成して、コマンド ライン上に構築できます。 Visual C++ は Visual C++ コンポーネント拡張 (C++/CX) をサポートしており、Windows ランタイム プログラミング モデルをターゲットにするための追加のタイプとオペレーターがあります。 C + を使用する/cli CX ユニバーサル Windows プラットフォーム (UWP)、Windows Phone 8.1、および Windows デスクトップ向けアプリをビルドします。 詳細については、次を参照してください。 [A ツアーの C+/cli CX](https://msdn.microsoft.com/magazine/dn166929.aspx)と[Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)します。  
  
 このチュートリアルでは、テキスト エディターを使って基本的な C++/CX プログラムを作成し、コマンド ラインでコンパイルします。 (表示されているプログラムをタイプするのではなく、自分の C++/CX プログラムを使用するか、別のヘルプ記事の C++/CX コード サンプルを使用できます。 この手法は UI 要素が含まれていない小さなモジュールをビルドおよびテストするのに便利です。)  
  
> [!NOTE]
>  Visual Studio IDE を使って C++/CX プログラムをコンパイルすることもできます。 IDE には、設計、デバッグ、エミュレーション、およびコマンド ラインでは利用できないデプロイのサポートが含まれているために、IDE を使用して、ユニバーサル Windows プラットフォーム (UWP) アプリを構築することをお勧めします。 詳細については、次を参照してください。[で C++ UWP アプリの作成](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)です。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 C++ 言語の基本を理解している必要があります。  
  
## <a name="compiling-a-ccx-program"></a>C++/CX プログラムのコンパイル  
 C++ のコンパイルを有効にする/cli CX が使用する必要があります、 [/ZW](../build/reference/zw-windows-runtime-compilation.md)コンパイラ オプション。 Visual C++ コンパイラは、Windows Runtime をターゲットにする .exe ファイルを生成し、必要なライブラリにリンクします。  
  
#### <a name="to-compile-a-ccx-application-on-the-command-line"></a>コマンド ラインで C++/CX アプリケーションをコンパイルするには:  
  
1.  開く、**開発者コマンド プロンプト**ウィンドウ。 (上、**開始**ウィンドウを開いて、**アプリ**します。 開く、 **Visual Studio Tools** 、バージョンの Visual Studio は、下のフォルダーをクリックして、**開発者コマンド プロンプト**ショートカットです)。開発者コマンド プロンプト ウィンドウを開く方法の詳細については、次を参照してください。[コマンドラインでビルドの c/c++ コード](../build/building-on-the-command-line.md)します。  
  
     コンピューターのオペレーティング システムと構成によっては、コードを正常にコンパイルするために管理者の資格情報が必要な場合があります。 を管理者としてコマンド プロンプト ウィンドウを実行するには、のショートカット メニューを開き**開発者コマンド プロンプト**選び、**管理者として実行**します。  
  
2.  コマンド プロンプトで次のように入力します。**メモ帳」と**します。  
  
     選択**はい**されたらファイルを作成します。  
  
3.  メモ帳で、次の行を入力します。  
  
    ```cpp  
    using namespace Platform;  
  
    int main(Platform::Array<Platform::String^>^ args)  
    {  
        Platform::Details::Console::WriteLine("This is a C++/CX program.");  
    }  
  
    ```  
  
4.  メニュー バーで、**ファイル**、**保存**します。  
  
     Windows ランタイムを使用する Visual C ソース ファイルを作成した[Platform 名前空間](../cppcx/platform-namespace-c-cx.md)名前空間。  
  
5.  コマンド プロンプトで次のように入力します。 **cl/EHsc/ZW」と/link/SUBSYSTEM:CONSOLE**します。 cl.exe コンパイラは、ソース コードを .obj ファイルにコンパイルした後、リンカーを実行して basiccx.exe という名前の実行プログラムを生成します。 (、 [/EHsc](../build/reference/eh-exception-handling-model.md)コンパイラ オプションは、C++ 例外処理モデルを指定し、 [/link](../build/reference/link-pass-options-to-linker.md)フラグをコンソール アプリケーションを指定します)。  
  
6.  コマンド プロンプトで、basiccx.exe プログラムを実行する入力**basiccx**します。  
  
     プログラムは、次のテキストを表示して終了します。  
  
    ```Output  
    This is a C++/CX program.  
    ```  
  
## <a name="see-also"></a>関連項目  
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)   
 [コンパイラ オプション](../build/reference/compiler-options.md)