---
description: 詳細については、「デスクトップアプリケーション (Visual C++)」を参照してください。
title: デスクトップ アプリケーション (Visual C++)
ms.date: 07/28/2019
ms.assetid: a020b534-293c-44e2-aa48-516c43ddeb8f
ms.topic: overview
ms.openlocfilehash: eb7badb73af507d31c9dd982f0a6189362249a3b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114755"
---
# <a name="desktop-applications-visual-c"></a>デスクトップ アプリケーション (Visual C++)

C++ の *デスクトップアプリケーション* は、Windows api の完全なセットにアクセスできるネイティブアプリケーションであり、ウィンドウまたはシステムコンソールで実行されます。 C++ のデスクトップアプリケーションは windows 10 を通じて Windows XP で実行できます (ただし、Windows XP は正式にはサポートされなくなり、その後に導入された Windows Api は多数あります)。

デスクトップアプリケーションは、Windows 10 を実行する Pc 上でも、XBox、Windows Phone、Surface Hub、およびその他のデバイスでも実行できるユニバーサル Windows プラットフォーム (UWP) アプリとは異なります。 デスクトップと UWP アプリケーションの詳細については、「 [テクノロジを選択する](/windows/win32/choose-your-technology)」を参照してください。

## <a name="desktop-bridge"></a>デスクトップ ブリッジ

Windows 10 では、既存のデスクトップアプリケーションまたは COM オブジェクトを UWP アプリとしてパッケージ化し、タッチなどの UWP 機能を追加したり、最新の Windows API セットから Api を呼び出したりすることができます。 また、UWP アプリを Visual Studio のデスクトップソリューションに追加し、1つのパッケージにまとめてパッケージ化し、Windows Api を使用してそれらの間で通信を行うこともできます。

Visual Studio 2017 バージョン15.4 以降では、Windows アプリケーションパッケージプロジェクトを作成して、既存のデスクトップアプリケーションをパッケージ化する作業を大幅に簡略化できます。 デスクトップアプリケーションで使用するレジストリ呼び出しまたは Api に関していくつかの制限が適用されますが、多くの場合、アプリケーションパッケージで実行中に同様の機能を実現する代替コードパスを作成できます。 詳細については、[デスクトップ ブリッジ](/windows/uwp/porting/desktop-to-uwp-root)に関するページをご覧ください。

## <a name="terminology"></a>用語

- *Win32* アプリケーションは、C++ の windows デスクトップアプリケーションであり、ネイティブな [windows C Api や COM api](/windows/win32/apiindex/windows-api-list) 、CRT、標準ライブラリ api、およびサードパーティ製のライブラリを利用できます。 ウィンドウで実行される Win32 アプリケーションでは、開発者が Windows プロシージャ関数内で Windows メッセージを明示的に操作する必要があります。 名前にかかわらず、Win32 アプリケーションは、32ビット (x86) または64ビット (x64) のバイナリとしてコンパイルできます。 Visual Studio IDE では、x86 と Win32 という用語は同義です。

- [コンポーネントオブジェクトモデル (COM)](/windows/win32/com/the-component-object-model)は、さまざまな言語で記述されたプログラムが相互に通信できるようにするための仕様です。 多くの Windows コンポーネントは COM オブジェクトとして実装され、オブジェクトの作成、インターフェイスの検出、およびオブジェクトの破棄に関する標準的な COM 規則に従います。  C++ デスクトップアプリケーションから COM オブジェクトを使用するのは比較的簡単ですが、独自の COM オブジェクトを作成する方がより高度です。 [Active Template Library (ATL)](../atl/atl-com-desktop-components.md)には、COM 開発を簡略化するマクロとヘルパー関数が用意されています。

- MFC アプリケーションは、ユーザーインターフェイスを作成するために [Microsoft Foundation Classes](../mfc/mfc-desktop-applications.md) を使用する Windows デスクトップアプリケーションです。 MFC アプリケーションでは、CRT および標準ライブラリの Api だけでなく、COM コンポーネントを使用することもできます。 MFC は、ウィンドウメッセージループと Windows Api に対して、シン C++ オブジェクト指向ラッパーを提供します。 MFC は、多くのユーザーインターフェイスコントロールまたはカスタムユーザーコントロールを持つアプリケーション (特にエンタープライズ型のアプリケーション) の既定の選択肢です。 MFC には、ウィンドウの管理、シリアル化、テキスト操作、印刷、リボンなどの最新のユーザーインターフェイス要素に便利なヘルパークラスが用意されています。 MFC を効果的に使用するには、Win32 に精通している必要があります。

- C++/CLI アプリケーションまたはコンポーネントでは、c++ 構文の拡張機能 (C++ 標準で許可されている) を使用して、.NET とネイティブの C + + コードの間の対話を可能にします。  C++/CLI アプリケーションは、ネイティブで実行される部分と、.NET 基底クラスライブラリへのアクセスを持つ .NET Framework で実行される部分を持つことができます。 C++/CLI は、C# または Visual Basic で記述されたコードを操作する必要があるネイティブ C++ コードがある場合に推奨されるオプションです。 これは、ユーザーインターフェイスコードではなく、.NET Dll で使用することを目的としています。 詳細については、「[C++/CLI による .NET プログラミング (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)」を参照してください。

C++ のすべてのデスクトップアプリケーションでは、C ランタイム (CRT) と標準ライブラリのクラスと関数、COM オブジェクト、および Windows API と総称されるパブリック Windows 関数を使用できます。 C++ での Windows デスクトップアプリケーションの概要については、「 [Win32 および c++](/windows/win32/LearnWin32/learn-to-program-for-windows)の概要」を参照してください。

## <a name="in-this-section"></a>このセクションの内容

|Title|説明|
|-----------|-----------------|
|[C++ による Windows コンソール アプリケーション](./overview-of-windows-programming-in-cpp.md)|コンソール アプリに関する情報が含まれています。 Win32 (または Win64) コンソール アプリケーションには、独自のウィンドウとメッセージ ループはありません。 コンソール ウィンドウで動作し、入出力はコマンド ラインを使用して扱われます。|
|[チュートリアル: Windows デスクトップ アプリケーション (C++) の作成](walkthrough-creating-windows-desktop-applications-cpp.md)|単純な Windows デスクトップアプリケーションを作成します。|
|[空の Windows デスクトップ アプリケーションを作成する](./overview-of-windows-programming-in-cpp.md)|既定のファイルを持たない Windows デスクトッププロジェクトを作成する方法。|
|[空の Win32 アプリケーションへのファイルの追加](./overview-of-windows-programming-in-cpp.md)|空のプロジェクトにファイルを追加する方法。|
|[リソース ファイルの操作](working-with-resource-files.md)|画像、アイコン、文字列テーブル、およびその他のリソースをデスクトップアプリケーションに追加する方法。|
|[DirectX を使用するゲームを作成するためのリソース (C++)](resources-for-creating-a-game-using-directx.md)|C++ でゲームを作成するためのコンテンツへのリンク。|
|[チュートリアル: スタティック ライブラリの作成と使用](../build/walkthrough-creating-and-using-a-static-library-cpp.md)|.lib バイナリ ファイルを作成する方法。|
|[方法: windows デスクトップアプリケーションで Windows 10 SDK を使用する](how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Windows 10 SDK を使用してビルドするプロジェクトの設定手順が示されています。|

## <a name="related-articles"></a>関連トピック

|Title|説明|
|-----------|-----------------|
|[Windows 開発](/windows/win32/index)|Windows API と COM に関する情報が含まれています (一部の Windows API とサードパーティ製 DLL は、COM オブジェクトとして実装されています)。|
|[Hilo: Windows 7 対応 C++ アプリケーションの開発](/previous-versions/msdn10/ff708696(v=msdn.10))|手荷物の受け取り場所に基づくユーザー インターフェイスを作成するために、Windows Animation と Direct2D を使用するリッチ クライアントの Windows デスクトップ アプリケーションを作成する方法について説明します。  このチュートリアルは、Windows 7 以降では更新されていませんが、Win32 プログラミングについて詳しく説明しています。|
|[C++ での Windows プログラミングの概要](overview-of-windows-programming-in-cpp.md)|C++ での Windows デスクトッププログラミングの主な機能について説明します。|

## <a name="see-also"></a>関連項目

[Visual Studio での C++](../overview/visual-cpp-in-visual-studio.md)
