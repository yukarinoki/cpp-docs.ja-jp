---
title: C と C++ プロジェクトおよび Visual Studio でのビルド システム
ms.description: Use Visual Studio to compile and build C++ projects for Windows, ARM or Linux based on any project system.
ms.date: 12/08/2018
f1_keywords:
- vcbuilding
- buildingaprogramVC
helpviewer_keywords:
- builds [C++]
- Visual C++ projects, building
- projects [C++], building
- builds [C++], options
- Visual C++, build options
ms.assetid: fa6ed4ff-334a-4d99-b5e2-a1f83d2b3008
ms.openlocfilehash: 73797f3817338c48e8ff11eaaadff71263374fd0
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64341171"
---
# <a name="cc-projects-and-build-systems-in-visual-studio"></a>C と C++ プロジェクトおよび Visual Studio でのビルド システム

Visual Studio 2017 を使用して、編集、コンパイル、Visual Studio プロジェクトまたは MSVC ツールセットでコンパイルにコードを変換することがなく任意の C++ コードを完全に IntelliSense サポート ベースを構築することができます。 たとえば、Windows コンピューターで、Visual Studio でクロスプラット フォームで CMake プロジェクトを編集し、リモート Linux マシンで g++ を使用して Linux 用にコンパイルします。

## <a name="c-compilation"></a>C++ のコンパイル

*ビルド*C++ プログラムは、1 つまたは複数のファイルからソース コードをコンパイルし、それらのファイルを実行可能ファイル (.exe)、動的に読み込むライブラリ (.dll)、またはスタティック ライブラリ (.lib) にリンクすることを意味します。 

基本的な C++ のコンパイルでは、次の 3 つの主な手順があります。

- C++ プリプロセッサは、各ソース ファイルのすべての #directives とマクロの定義を変換します。 これを作成、*翻訳単位*します。
- C++ コンパイラでは、設定されているどのようなコンパイラ オプションを適用するのには、オブジェクト ファイル (.obj) 各翻訳単位をコンパイルします。
- *リンカー*オブジェクト ファイルが設定されているリンカー オプションを適用する、1 つ実行可能ファイルにマージします。 

## <a name="the-msvc-toolset"></a>MSVC ツールセット

MicrosoftC++コンパイラ、リンカー、標準ライブラリ、および関連のユーティリティは、MSVC コンパイラ ツールセット (、ツール チェーン、または「ビルド ツール」とも呼ばれます) を構成します。 Visual Studio では、これらが含まれます。 ダウンロードしてから無料のスタンドアロン パッケージとして、ツールセットを使用することができますも、 [Build Tools for Visual Studio 2017 のダウンロード場所](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2017)します。

MSVC コンパイラ (cl.exe) 直接コマンドラインから呼び出すことによって、単純なプログラムを構築できます。 次のコマンドを呼び出すと呼ばれる実行可能ファイルをビルドする cl.exe 受け取り 1 つのソース コード ファイルでは、 *hello.exe*: 

```cmd
cl /EHsc hello.cpp
```
C++ プリプロセッサとリンカーが最終出力ファイルを生成するためにここで、コンパイラ (cl.exe) によって自動的に起動に注意してください。  詳細については、次を参照してください。[コマンドライン上に構築](building-on-the-command-line.md)します。

## <a name="build-systems-and-projects"></a>システムとプロジェクトをビルドします。

ほとんどの現実のプログラムがいくつかの種類に使用*ビルド システム*の複数の構成の複数のソース ファイルをコンパイルする複雑さを管理する (つまりデバッグとリリース)、複数のプラットフォーム (x86、x64、ARM など)、カスタム ビルド手順、および実行可能ファイルの複数あっても、特定の順序でコンパイルする必要があります。 ビルドの構成ファイルで設定を行うし、コンパイラを呼び出す前に、ビルド システムが入力としてそのファイルを受け取ります。 ソース コード ファイルと実行可能ファイルを作成するために必要なビルド構成ファイルのセットと呼ばれる、*プロジェクト*します。 

Visual Studio プロジェクトに C++ のさまざまなオプションを次に示します。

- Visual Studio IDE を使用して Visual Studio プロジェクトを作成し、プロパティ ページを使用して構成します。 Visual Studio プロジェクトでは、Windows 上で実行されるプログラムを生成します。 概要については、次を参照してください。[のコンパイルとビルド](/visualstudio/ide/compiling-and-building-in-visual-studio)、Visual Studio ドキュメント。

- CMakeLists.txt ファイルが含まれるフォルダーを開きます。 CMake のサポートは Visual Studio に統合します。 IDE を使用して、編集、テスト、および任意の方法での CMake ファイルを変更せずにデバッグすることができます。 これにより、さまざまなエディターを使用した、他のユーザーとの CMake の同じプロジェクトで作業することができます。 CMake は、クロス プラットフォーム開発のための推奨されるアプローチです。 詳細については、次を参照してください。 [CMake プロジェクト](cmake-projects-in-visual-studio.md)します。
 
- プロジェクト ファイルを持たないソース ファイルの緩やかなフォルダーを開きます。 Visual Studio は、ファイルをビルドするのにヒューリスティックを使用します。 これは、コンパイルして小さなコンソール アプリケーションを実行する簡単な方法です。 詳細については、次を参照してください。[フォルダーを開くプロジェクト](open-folder-projects-cpp.md)します。

- メイクファイルでまたはその他のビルド システムの構成ファイルを含むフォルダーを開きます。 JSON ファイルをフォルダーに追加することで、任意のビルド コマンドを起動する Visual Studio を構成することができます。 詳細については、次を参照してください。[フォルダーを開くプロジェクト](open-folder-projects-cpp.md)します。
 
- Visual Studio では、Windows のメイクファイルを開きます。 詳細については、次を参照してください。 [NMAKE リファレンス](reference/nmake-reference.md)します。

## <a name="msbuild-from-the-command-line"></a>コマンドラインから MSBuild 

コマンド ライン オプションと共に .vcxproj ファイルを渡すことによって、コマンドラインから MSBuild を呼び出すことができます。 この方法では、MSBuild、十分に理解を必要とし、どうしても必要な場合にのみお勧めします。 詳細については、「[MSBuild](msbuild-visual-cpp.md)」を参照してください。

## <a name="in-this-section"></a>このセクションの内容

[Visual Studio プロジェクト](creating-and-managing-visual-cpp-projects.md)ネイティブを使用して Visual Studio でプロジェクトのビルド システム (MSBuild) を作成、構成、および C++ を構築する方法。

[CMake プロジェクト](cmake-projects-in-visual-studio.md)コード、ビルド、および Visual Studio で CMake プロジェクトをデプロイする方法。

[フォルダーのプロジェクトを開く](open-folder-projects-cpp.md)任意の任意のビルド システム、またはビルド システムのないに基づいて、Visual Studio を使用して、コーディング、ビルド、C++ プロジェクトをデプロイする方法。 全然です。 

[リリース ビルド](release-builds.md)エンドユーザーへの展開を作成および最適化されたリリースをトラブルシューティングする方法を構築します。

[コマンド ラインから MSVC ツールセットを使用する](building-on-the-command-line.md)<br/>
C と C++ コンパイラを使用し、Visual Studio IDE を使用するのではなく、コマンドラインから直接ツールを構築する方法について説明します。

[Visual Studio で Dll をビルド](dlls-in-visual-cpp.md)作成、デバッグ、および Visual Studio で C/C++ Dll (共有ライブラリ) をデプロイする方法。

[チュートリアル: スタティック ライブラリの作成と](walkthrough-creating-and-using-a-static-library-cpp.md).lib バイナリ ファイルを作成する方法。

[C/C++ 分離アプリケーションとサイド バイ サイド アセンブリをビルド](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)分離アプリケーションとサイド バイ サイド アセンブリの概念に基づく、Windows デスクトップ アプリケーションのデプロイ モデルについて説明します。

[64 ビット、x64 用の C++ プロジェクトの構成のターゲット](configuring-programs-for-64-bit-visual-cpp.md)ハードウェア、MSVC のビルド ツール 64 ビット x64 を対象とする方法。

[ARM プロセッサ用の C++ プロジェクトを構成する](configuring-programs-for-arm-processors-visual-cpp.md)MSVC のビルド ツールを使用して、ARM ハードウェアを対象にする方法。

[コードの最適化](optimizing-your-code.md)ガイド付きプログラムの最適化を含むさまざまな方法でコードを最適化する方法。

[Windows XP 用プログラムを構成する](configuring-programs-for-windows-xp.md)ターゲットが Windows XP、MSVC がツールを構築する方法。

[C/C++ ビルドのリファレンス](reference/c-cpp-building-reference.md)<br/>
C++ でのプログラムのビルド、コンパイラ オプションとリンカー オプション、およびさまざまなビルド ツールに関する参照記事へのリンクがあります。
