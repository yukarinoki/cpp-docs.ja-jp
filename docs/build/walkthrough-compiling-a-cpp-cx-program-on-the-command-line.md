---
title: 'チュートリアル: コマンド ラインでの C++/CX プログラムのコンパイル'
ms.date: 04/23/2019
ms.assetid: 626f5544-69ed-4736-83a9-f11389b371b2
ms.openlocfilehash: 83369fc7b458463ea1f44a347bbcd0ca4eb32224
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078204"
---
# <a name="walkthrough-compiling-a-ccx-program-on-the-command-line"></a>チュートリアル: コマンド ラインでの C++/CX プログラムのコンパイル

> [!NOTE]
> 新しい UWP アプリとコンポーネントでは、Windows ランタイム API の標準 C++17 言語投影である [C++/WinRT](/windows/uwp/cpp-and-winrt-apis/) を使用することをお勧めします。 C++/WinRT は、Windows 10 SDK のバージョン 1803 以降で使用できます。 C++/WinRT は、全体がヘッダー ファイル内に実装され、最新の Windows API に対する最高級のアクセスを提供するように設計されています。

Microsoft C++ コンパイラ (MSVC) では Visual C++ コンポーネント拡張機能 (C++/CX) がサポートされ、Windows ランタイム プログラミング モデルをターゲットとする型と演算子が追加されています。 C++/CX を使用して、ユニバーサル Windows プラットフォーム (UWP) と Windows デスクトップ用のアプリをビルドできます。 詳細については、「[C++/CX のツアー](https://msdn.microsoft.com/magazine/dn166929.aspx)」と[ランタイム プラットフォーム用のコンポーネント拡張機能](../extensions/component-extensions-for-runtime-platforms.md)に関する記事を参照してください。

このチュートリアルでは、テキスト エディターを使って基本的な C++/CX プログラムを作成し、コマンド ラインでコンパイルします。 (表示されているプログラムをタイプするのではなく、自分の C++/CX プログラムを使用するか、別のヘルプ記事の C++/CX コード サンプルを使用できます。 この手法は UI 要素が含まれていない小さなモジュールをビルドおよびテストするのに便利です)。

> [!NOTE]
> Visual Studio IDE を使って C++/CX プログラムをコンパイルすることもできます。 IDE には、コマンド ラインでは利用できない、設計、デバッグ、エミュレーション、および配置のサポートが含まれているため、ユニバーサル Windows プラットフォーム (UWP) アプリをビルドする場合は IDE を使用することをお勧めします。 詳細については、[C++ での UWP アプリの作成](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)に関する記事を参照してください。

## <a name="prerequisites"></a>前提条件

C++ 言語の基本を理解していること。

## <a name="compiling-a-ccx-program"></a>C++/CX プログラムのコンパイル

C++/CX のコンパイルを有効にするには、[/ZW](reference/zw-windows-runtime-compilation.md) コンパイラ オプションを使用する必要があります。 MSVC コンパイラによって、ターゲットが Windows ランタイムである .exe ファイルと、必要なライブラリへのリンクが生成されます。

#### <a name="to-compile-a-ccx-application-on-the-command-line"></a>コマンド ラインで C++/CX アプリケーションをコンパイルするには:

1. **[開発者コマンド プロンプト]** ウィンドウを開きます ( **[スタート]** ウィンドウで、 **[アプリ]** を開きます。 使用している Visual Studio のバージョンの下の **Visual Studio Tools** フォルダーを開き、 **[開発者コマンド プロンプト]** ショートカットを選択します)。開発者コマンド プロンプト ウィンドウを開く方法について詳しくは、「[コマンド ラインから MSVC ツールセットを使用する](building-on-the-command-line.md)」をご覧ください。

   コンピューターのオペレーティング システムと構成によっては、コードを正常にコンパイルするために管理者の資格情報が必要な場合があります。 管理者としてコマンド プロンプト ウィンドウを実行するには、 **[開発者コマンド プロンプト]** のショートカット メニューを開いて **[管理者として実行]** を選択します。

1. コマンド プロンプトで、「**notepad basiccx.cpp**」と入力します。

   ファイルを作成するかどうかを確認するメッセージが表示されたら、 **[はい]** を選択します。

1. メモ帳で、次の行を入力します。

    ```cpp
    using namespace Platform;

    int main(Platform::Array<Platform::String^>^ args)
    {
        Platform::Details::Console::WriteLine("This is a C++/CX program.");
    }
    ```

1. メニュー バーで、 **[ファイル]**  >  **[保存]** を選択します。

   Windows ランタイム [プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)を使用する C++ ソース ファイルが作成されました。

1. コマンド プロンプトで、「**cl /EHsc /ZW basiccx.cpp /link /SUBSYSTEM:CONSOLE**」と入力します。 cl.exe コンパイラは、ソース コードを .obj ファイルにコンパイルした後、リンカーを実行して basiccx.exe という名前の実行プログラムを生成します ([/EHsc](reference/eh-exception-handling-model.md) コンパイラ オプションは C++ 例外処理モデルを指定し、[/link](reference/link-pass-options-to-linker.md) フラグはコンソール アプリケーションを指定します)。

1. basiccx.exe プログラムを実行するには、コマンド プロンプトで「**basiccx**」と入力します。

   プログラムは、次のテキストを表示して終了します。

    ```Output
    This is a C++/CX program.
    ```

## <a name="see-also"></a>関連項目

[プロジェクトおよびビルド システム](projects-and-build-systems-cpp.md)<br/>
[MSVC コンパイラ オプション](reference/compiler-options.md)
