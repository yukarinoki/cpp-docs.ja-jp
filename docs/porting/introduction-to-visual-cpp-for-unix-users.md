---
title: Visual C++ の紹介 (UNIX ユーザー向け)
ms.date: 09/01/2017
helpviewer_keywords:
- UNIX [C++]
ms.assetid: 36108b31-e7fa-49a8-a1f7-7077fcbec873
ms.openlocfilehash: 0cffdc2be00b4af9badbbbc80bcfef48b3f76e19
ms.sourcegitcommit: 9e85c2e029d06b4c1c69837437468718b4d54908
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2019
ms.locfileid: "57818376"
---
# <a name="introduction-to-visual-c-for-unix-users"></a>Visual C++ の紹介 (UNIX ユーザー向け)

このトピックでは、Visual Studio を初めて使用し、C++ と Visual Studio 統合開発環境 (IDE) で生産性を向上したい UNIX ユーザー向けの情報を提供します。

## <a name="getting-started-on-the-command-line"></a>コマンドラインに関する概要

UNIX のコマンドライン環境を使用する場合と同様の方法で、コマンドラインから C++ コンパイラを使用できます。 コマンド ラインの C と C++ コンパイラ (CL.EXE)、リンカー (LINK.EXE)、Microsoft バージョンの UNIX make ユーティリティである NMAKE.EXE を含むその他のツールを使用して、コマンド プロンプトからコンパイルします。

UNIX では、コマンドは /usr/bin などの共通のフォルダーにインストールされます。 Visual Studio の場合、コマンドライン ツールは Visual Studio のインストール ディレクトリにインストールされます。VC\bin サブディレクトリとそのサブディレクトリです。 UNIX とは異なり、これらのツールは普通のコマンド プロンプト ウィンドウでは利用できません。 コマンドライン ツールを使用するには、開発者コマンド プロンプト ショートカットを使用するか、vcvarsall.bat など、開発者コマンド ファイルを実行してください。 これで、コマンド ラインから C++ プログラムをコンパイルするために必要なパスとその他の環境変数が設定されます。 詳細については、「[コマンドラインでの C/C++ コードのビルド](../build/building-on-the-command-line.md)」および「[チュートリアル: コマンド ラインでのネイティブ C++ プログラムのコンパイル](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)」を参照してください。

開発者コマンド プロンプト ショートカットを開くには、デスクトップの検索コントロールに「*developer command prompt*」と入力し、検索結果からお使いのバージョンの Visual Studio の**開発者コマンド プロンプト**を選びます。 特定のホストとターゲット アーキテクチャに事前構成した開発者コマンド プロンプトを選ぶには、**[スタート]** メニュー (デスクトップの隅にある Windows アイコン) を開き、お使いのバージョンの Visual Studio (**Visual Studio 2017** など) のフォルダーまでスクロールします。 フォルダーを開き、任意のホストとターゲット アーキテクチャのコマンド プロンプト ショートカットを選びます。

Visual Studio デバッガー、IntelliSense のコード参照とステートメント入力候補、ビジュアル デザイナー、プロジェクト管理など、さらに強力な機能を活用するには、Visual Studio IDE を使用する必要があります。

## <a name="debugging-your-code"></a>コードのデバッグ

コマンドラインを使用して開発用ワークステーションでアプリケーションを実行する場合、コードでメモリ アクセス違反、ハンドルされない例外や、その他の回復不能なエラーが発生したときに、Visual Studio デバッガーを実行するダイアログ ボックスが表示されます。 **[OK]** をクリックすると、Visual Studio の開発環境が起動し、障害発生時点でデバッガーが開きます。 この方法でアプリケーションをデバッグすることができますが、このケースでは、[/Z7、/Zi、/ZI (デバッグ情報の形式)](../build/reference/z7-zi-zi-debug-information-format.md) スイッチを使用してコンパイルした場合にのみ、ソースを利用できます。 詳細については、「[ネイティブ コードのデバッグ](/visualstudio/debugger/debugging-native-code)」および「[C++ デスクトップ開発のための Visual Studio IDE の使用](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)」を参照してください。

## <a name="using-the-development-environment"></a>開発環境を使用する

開発環境を使用すると、*プロジェクト*でソース コードを編集してビルドしやすくなります。 プロジェクトは、ライブラリまたは実行可能ファイルなどの 1 つの単位にコンパイルされる、ソースと関連ファイルのコレクションです。 プロジェクトには、ファイルをビルドする方法に関する情報も含まれます。 プロジェクトに関する情報は、拡張子が .prj のプロジェクト ファイルに格納されます。

それぞれが別のセットのコンパイラ オプションや別の言語でビルドされている可能性がある複数のライブラリおよび実行可能ファイルから構成されるアプリケーションは、1 つの*ソリューション*の一部である複数のプロジェクトに格納されます。 ソリューションは、複数のプロジェクトをグループ化するためのコンテナーの抽象化です。 プロジェクトに関する情報は、拡張子が .prj のプロジェクト ファイルに格納されます。 詳細については、「[Visual Studio のソリューションおよびプロジェクト](/visualstudio/ide/solutions-and-projects-in-visual-studio)」および「[C++ デスクトップ開発のための Visual Studio IDE の使用](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)」を参照してください。

## <a name="importing-your-existing-code"></a>既存のコードをインポートする

C++ コンパイラを使用すれば、メイクファイルでコンパイルするように設定した (メイクファイルを使わないことも可能) 既存のコードをビルドし、Visual Studio プロジェクトに配置できます。 詳細については、「[方法 :既存のコードから C++ プロジェクトを作成する](../build/how-to-create-a-cpp-project-from-existing-code.md)」を参照してください。

## <a name="creating-a-new-project"></a>新規プロジェクトの作成

開発環境では、新しいプロジェクトを作成できます。 Visual Studio はさまざまな共通プロジェクトの標準的なコードを提供する多数のテンプレートを提供します。 アプリケーション ウィザードを使用して、様々な種類のアプリケーション用のコードのアウトラインを持つプロジェクトを生成することができます。

まず、**コンソール アプリケーション (Win32) ウィザード**を使用して、空のプロジェクトを作成できます。 **[空のプロジェクト]** チェック ボックスをオンにします。 これで、新規および既存のファイルをプロジェクトに後で追加できます。

プロジェクトを作成するときに、プロジェクトの名前を付けてください。 既定では、プロジェクト名は、ダイナミック リンク ライブラリ (DLL) の名前またはプロジェクトからビルドされる実行可能ファイルと等しくなります。 詳細については、「[ソリューションとプロジェクトの作成](/visualstudio/ide/creating-solutions-and-projects)」を参照してください。

## <a name="microsoft-specific-modifiers"></a>Microsoft 固有の修飾子

Microsoft Visual C++ コンパイラは、Windows オペレーティング システムのプログラミングをサポートする目的で、標準 C++ プログラミング言語にいくつかの拡張機能を実装します。 これらの拡張機能は、ストレージ クラス属性、関数の呼び出し規約、ベース アドレス指定などを指定するために使用されます。 サポートされているすべての C++ の拡張機能の完全な一覧については、「[Microsoft 固有の修飾子](../cpp/microsoft-specific-modifiers.md)」を参照してください。


  `/Za` コンパイラ オプションを使用して、C++ へのすべての Microsoft 固有の拡張機能を無効にすることができます。 複数のプラットフォームで実行するコードを記述する場合、このオプションが推奨されます。 `/Za` コンパイラ オプションの詳細については、「[/Za、/Ze (言語拡張機能の無効化)](../build/reference/za-ze-disable-language-extensions.md)」を参照してください。 C++ コンパイラの準拠の詳細については、「[Visual C++ 言語への準拠](../visual-cpp-language-conformance.md)」および「[非標準動作](../cpp/nonstandard-behavior.md)」を参照してください。

## <a name="precompiled-headers"></a>プリコンパイル済みヘッダー

Microsoft C および C++ コンパイラは、インライン コードを含む、C または C++ コードをプリコンパイルするためのオプションを提供します。 このパフォーマンス機能を使用して、安定したコードの本体をコンパイルし、ファイル内のコードのコンパイル済みの状態を格納します。さらに、後続のコンパイル中に、プリコンパイルされたコードと開発中のコードを結合できます。 安定したコードは再コンパイルする必要がないので、後続のコンパイルが高速化します。

既定では、プリコンパイル済みのすべてのコードは、ファイル stdafx.h と stdafx.cpp で指定されます。 **[プリコンパイル済みヘッダー]** オプションをオフにしない限り、**[新しいプロジェクト]** ウィザードは自動的にこれらのファイルを作成します。 プリコンパイルされたヘッダーの詳細については、「[プリコンパイル済みヘッダー ファイルの作成](../build/creating-precompiled-header-files.md)」を参照してください。

## <a name="related-sections"></a>関連項目

詳細については、「[UNIX から Win32 への移植](../porting/porting-from-unix-to-win32.md)」を参照してください。

## <a name="see-also"></a>関連項目

[プロジェクトおよびビルド システム](../build/projects-and-build-systems-cpp.md)
