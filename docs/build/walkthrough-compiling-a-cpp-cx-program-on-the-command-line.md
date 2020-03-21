---
title: 'チュートリアル: コマンド ラインでの C++/CX プログラムのコンパイル'
ms.date: 04/23/2019
ms.assetid: 626f5544-69ed-4736-83a9-f11389b371b2
ms.openlocfilehash: 83369fc7b458463ea1f44a347bbcd0ca4eb32224
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078204"
---
# <a name="walkthrough-compiling-a-ccx-program-on-the-command-line"></a>チュートリアル: コマンド ラインでの C++/CX プログラムのコンパイル

> [!NOTE]
> 新しい UWP アプリとコンポーネントの場合は、Windows ランタイム api の標準 c++ 17 言語プロジェクションである[ C++/WinRT](/windows/uwp/cpp-and-winrt-apis/)を使用することをお勧めします。 C++/WinRT はバージョン 1803 以降から Windows 10 SDK で使用できます。 C++/WinRT はヘッダー ファイル、完全に実装されは最新の Windows API にファースト クラスのアクセス提供するために設計されています。

Microsoft C++コンパイラ (MSVC) は、 C++コンポーネント拡張 (C++/cx) をサポートしています。これには、Windows ランタイムプログラミングモデルを対象とする追加の型と演算子が含まれています。 /Cx を使用C++して、ユニバーサル WINDOWS プラットフォーム (UWP) と Windows デスクトップ用のアプリを構築できます。 詳細については、「[ランタイムプラットフォームの/cx およびコンポーネント拡張機能](../extensions/component-extensions-for-runtime-platforms.md)[のC++](https://msdn.microsoft.com/magazine/dn166929.aspx)概要」を参照してください。

このチュートリアルでは、テキスト エディターを使って基本的な C++/CX プログラムを作成し、コマンド ラインでコンパイルします。 (表示されているプログラムをタイプするのではなく、自分の C++/CX プログラムを使用するか、別のヘルプ記事の C++/CX コード サンプルを使用できます。 この手法は、UI 要素のない小さなモジュールをビルドしてテストする場合に便利です)。

> [!NOTE]
> Visual Studio IDE を使って C++/CX プログラムをコンパイルすることもできます。 IDE には、コマンドラインでは使用できない設計、デバッグ、エミュレーション、および配置のサポートが含まれているため、IDE を使用してユニバーサル Windows プラットフォーム (UWP) アプリをビルドすることをお勧めします。 詳細については、「 [」のC++「UWP アプリの作成](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)」を参照してください。

## <a name="prerequisites"></a>前提条件

C++言語の基本を理解します。

## <a name="compiling-a-ccx-program"></a>C++/CX プログラムのコンパイル

/Cx のC++コンパイルを有効にするには、 [/ZW](reference/zw-windows-runtime-compilation.md)コンパイラオプションを使用する必要があります。 MSVC コンパイラは、Windows ランタイムを対象とする .exe ファイルを生成し、必要なライブラリへのリンクを作成します。

#### <a name="to-compile-a-ccx-application-on-the-command-line"></a>コマンド ラインで C++/CX アプリケーションをコンパイルするには:

1. **開発者コマンドプロンプト**ウィンドウを開きます。 ( **[スタート]** ウィンドウで、 **[アプリ]** を開きます。 使用している Visual Studio のバージョンの下にある**Visual Studio Tools**フォルダーを開き、**開発者コマンドプロンプト**ショートカットを選択します)。開発者コマンドプロンプトウィンドウを開く方法の詳細については、「[コマンドラインからの MSVC ツールセットの使用](building-on-the-command-line.md)」を参照してください。

   コンピューターのオペレーティング システムと構成によっては、コードを正常にコンパイルするために管理者の資格情報が必要な場合があります。 管理者としてコマンドプロンプトウィンドウを実行するには、**開発者コマンドプロンプト**のショートカットメニューを開き、 **[管理者として実行]** を選択します。

1. コマンドプロンプトで、「 **notepad basiccx**と入力します。

   ファイルの作成を求めるメッセージが表示されたら、[**はい]** を選択します。

1. メモ帳で、次の行を入力します。

    ```cpp
    using namespace Platform;

    int main(Platform::Array<Platform::String^>^ args)
    {
        Platform::Details::Console::WriteLine("This is a C++/CX program.");
    }
    ```

1. メニューバーで、[**ファイル** > **保存**] を選択します。

   Windows ランタイム[Platform 名前](../cppcx/platform-namespace-c-cx.md)空間C++を使用するソースファイルを作成しました。

1. コマンドプロンプトで、「 **cl/EHSC/ZW basiccx. .cpp/LINK/SUBSYSTEM: CONSOLE**」と入力します。 cl.exe コンパイラは、ソース コードを .obj ファイルにコンパイルした後、リンカーを実行して basiccx.exe という名前の実行プログラムを生成します。 ( [/Ehsc](reference/eh-exception-handling-model.md)コンパイラオプションはC++例外処理モデルを指定し、 [/link](reference/link-pass-options-to-linker.md)フラグはコンソールアプリケーションを指定します)。

1. Basiccx.exe .exe プログラムを実行するには、コマンドプロンプトで「 **basiccx.exe**」と入力します。

   プログラムは、次のテキストを表示して終了します。

    ```Output
    This is a C++/CX program.
    ```

## <a name="see-also"></a>参照

[プロジェクトおよびビルド システム](projects-and-build-systems-cpp.md)<br/>
[MSVC コンパイラ オプション](reference/compiler-options.md)
