---
title: Visual Studio の C/C++ プロジェクトとビルド システム
ms.description: Use Visual Studio to compile and build C++ projects for Windows, ARM or Linux based on any project system.
ms.date: 07/17/2019
helpviewer_keywords:
- builds [C++]
- C++ projects, building
- projects [C++], building
- builds [C++], options
- C++, build options
ms.assetid: fa6ed4ff-334a-4d99-b5e2-a1f83d2b3008
ms.topic: overview
ms.openlocfilehash: 3d82ac4569e06a4472047a79da60032ad2db43ca
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078470"
---
# <a name="cc-projects-and-build-systems-in-visual-studio"></a>Visual Studio の C/C++ プロジェクトとビルド システム

IntelliSense がフル サポートされている Visual Studio を使用して、C++ コード ベースを編集、コンパイル、およびビルドできます。そのコードを Visual Studio プロジェクトに変換したり、MSVC ツールセットを使用してコンパイルしたりする必要はありません。 たとえば、Windows コンピューター上の Visual Studio でクロスプラットフォームの CMake プロジェクトを編集した後、リモート Linux コンピューター上で g++ を使用してそれを Linux 用にコンパイルできます。

## <a name="c-compilation"></a>C++ のコンパイル

C++ プログラムの "*ビルド*" とは、1 つ以上のファイルからソース コードをコンパイルし、それらのファイルを実行可能ファイル (.exe)、動的読み込みライブラリ (.dll)、またはスタティック ライブラリ (.lib) にリンクすることを意味します。

C++ の基本的なコンパイルには、次の 3 つの主要な手順が含まれます。

- C++ プリプロセッサによって、各ソース ファイル内のすべての # ディレクティブとマクロの定義が変換されます。 これにより、"*翻訳単位*" が作成されます。
- C++ コンパイラによって、各翻訳単位がオブジェクト ファイル (.obj) にコンパイルされます。設定されているすべてのコンパイラ オプションが適用されます。
- "*リンカー*" によって、オブジェクト ファイルが単一の実行可能ファイルにマージされます。設定されているリンカー オプションが適用されます。

## <a name="the-msvc-toolset"></a>MSVC ツールセット

MSVC コンパイラ ツールセット (ツールチェーンまたは "ビルド ツール" とも呼ばれます) は、Microsoft C++ コンパイラ、リンカー、標準ライブラリ、および関連ユーティリティによって構成されます。 これらは、Visual Studio に含まれています。 [Visual Studio 2019 用のビルド ツールのダウンロード場所](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019)からツールセットをスタンドアロン パッケージとして無料でダウンロードして使用することもできます。

コマンド ラインから MSVC コンパイラ (cl.exe) を直接呼び出すことで、単純なプログラムをビルドできます。 次のコマンドでは、単一のソース コード ファイルを受け入れ、cl.exe を呼び出して *hello .exe* という名前の実行可能ファイルがビルドされます。

```cmd
cl /EHsc hello.cpp
```

ここで、コンパイラ (cl.exe) によって C++ プリプロセッサとリンカーが自動的に呼び出され、最終的な出力ファイルが生成されることに注意してください。  詳細については、[コマンド ラインでのビルド](building-on-the-command-line.md)に関するページを参照してください。

## <a name="build-systems-and-projects"></a>ビルド システムとプロジェクト

ほとんどの実際のプログラムでは、何らかの種類の "*ビルド システム*" を使用して、複数の構成 (つまりデバッグとリリース)、複数のプラットフォーム (x86、x64、ARM など)、カスタム ビルド ステップ用の複数のソース ファイルのコンパイル、および特定の順序でコンパイルする必要がある複数の実行可能ファイルのコンパイルという複雑な処理が管理されます。 ビルド構成ファイル内に設定すると、コンパイラが呼び出される前に、ビルド システムによってそのファイルが入力として使用されます。 実行可能ファイルをビルドするために必要なソース コード ファイルとビルド構成ファイルのセットを "*プロジェクト*" と呼びます。

次の一覧に、Visual Studio プロジェクトの C++ 用のさまざまなオプションを示します。

- Visual Studio IDE を使用して Visual Studio プロジェクトを作成し、プロパティ ページを使用して構成する。 Visual Studio プロジェクトでは、Windows 上で実行されるプログラムが生成されます。 概要については、Visual Studio ドキュメントの「[コンパイルとビルド](/visualstudio/ide/compiling-and-building-in-visual-studio)」を参照してください。

- CMakeLists.txt ファイルが含まれているフォルダーを開く。 Visual Studio には CMake のサポートが統合されています。 IDE を使用して、CMake ファイルをどのような形でも変更せずに、編集、テスト、およびデバッグすることができます。 これにより、異なるエディターを使用している可能性のある他のユーザーと同じ CMake プロジェクトで作業することができます。 CMake は、クロスプラットフォームの開発に推奨されるアプローチです。 詳細については、「[CMake プロジェクト](cmake-projects-in-visual-studio.md)」をご覧ください。

- プロジェクト ファイルのないソース ファイルのルーズ フォルダーを開く。 Visual Studio では、ヒューリスティックを使用してファイルがビルドされます。 これは、小さなコンソール アプリケーションをコンパイルして実行する簡単な方法です。 詳細については、[フォルダー プロジェクトのオープン](open-folder-projects-cpp.md)に関する記事を参照してください。

- メイクファイルまたはその他のビルド システムの構成ファイルが含まれているフォルダーを開く。 JSON ファイルをフォルダーに追加することで、任意のビルド コマンドを呼び出すように Visual Studio を構成できます。 詳細については、[フォルダー プロジェクトのオープン](open-folder-projects-cpp.md)に関する記事を参照してください。

- Visual Studio で Windows メイクファイルを開く。 詳細については、「[NMAKE リファレンス](reference/nmake-reference.md)」を参照してください。

## <a name="msbuild-from-the-command-line"></a>コマンド ラインからの MSBuild

.vcxproj ファイルをコマンドライン オプションと共に渡すことによって、コマンド ラインから MSBuild を呼び出すことができます。 この方法では MSBuild を十分に理解している必要があり、絶対に必要な場合にのみ推奨されます。 詳細については、「[MSBuild](msbuild-visual-cpp.md)」を参照してください。

## <a name="in-this-section"></a>このセクションの内容

[Visual Studio プロジェクト](creating-and-managing-visual-cpp-projects.md): Visual Studio でネイティブ ビルド システム (MSBuild) を使用して C++ プロジェクトを作成、構成、およびビルドする方法。

[CMake プロジェクト](cmake-projects-in-visual-studio.md): Visual Studio で CMake プロジェクトをコーディング、ビルド、および配置する方法。

[フォルダー プロジェクトを開く](open-folder-projects-cpp.md): Visual Studio を使用して、任意のビルド システムに基づいて、またはビルド システムなしで、C++ プロジェクトをコーディング、ビルド、および配置する 方法。

[リリース ビルド](release-builds.md): エンド ユーザーに対する配置用に最適化されたリリース ビルドの作成およびトラブルシューティングを行う方法。

[コマンド ラインから MSVC ツールセットを使用する](building-on-the-command-line.md)<br/>
Visual Studio IDE を使用するのではなく、C/C コンパイラとビルド ツールをコマンド ラインから直接使用する方法について説明します。

[Visual Studio での DLL のビルド](dlls-in-visual-cpp.md): Visual Studio で C/C++ DLL (共有ライブラリ) を作成、デバッグ、および配置する方法。

[チュートリアル: スタティック ライブラリの作成と使用](walkthrough-creating-and-using-a-static-library-cpp.md): .lib バイナリ ファイルの作成方法。

[C/C++ 分離アプリケーションと side-by-side アセンブリのビルド](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md): アプリケーションの分離、side-by-side アセンブリなどの考え方に基づく Windows デスクトップ アプリケーションの配置モデルについて説明します。

[ターゲットが 64 ビットの x64 用の C++ プロジェクトを構成する](configuring-programs-for-64-bit-visual-cpp.md): MSVC ビルド ツールを使用して、64 ビットの x64 ハードウェアをターゲットにする方法。

[ARM プロセッサ用の C++ プロジェクトを構成する](configuring-programs-for-arm-processors-visual-cpp.md): MSVC ビルド ツールを使用して ARM ハードウェアをターゲットにする方法。

[コードの最適化](optimizing-your-code.md): プログラムによるガイド付き最適化を含むさまざまな方法でコードを最適化する方法。

[Windows XP 用プログラムの構成](configuring-programs-for-windows-xp.md): MSVC ビルド ツールを使用して Windows XP をターゲットにする方法。

[C/C++ ビルドのリファレンス](reference/c-cpp-building-reference.md)<br/>
C++ でのプログラムのビルド、コンパイラ オプションとリンカー オプション、およびさまざまなビルド ツールに関する参照記事へのリンクがあります。
