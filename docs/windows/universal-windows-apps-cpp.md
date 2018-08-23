---
title: ユニバーサル Windows アプリ (C++) |Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7ba556ee3803bb00f07032e0589209af2d32addf
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591754"
---
# <a name="universal-windows-apps-c"></a>ユニバーサル Windows アプリ (C++)

ユニバーサル Windows プラットフォーム (UWP) アプリは、一連のさまざまなデバイスでさまざまな画面サイズに合わせて調整されるコンテンツの中心はシンプルなユーザー インターフェイスを重視する設計原則を具体化します。 XAML マークアップで UI を作成し、ネイティブ C++ で分離コードを作成します。 さらに他の言語で記述された UWP アプリケーションで使用可能なコンポーネント (DLL) を作成できます。 UWP アプリの API サーフェスは、Windows ランタイムのさまざまなオペレーティング システム サービスを提供するための十分に考慮されたライブラリです。

> [!TIP]
> Windows 10 では、Microsoft Store から展開の既存のデスクトップ アプリケーションをパッケージ化するデスクトップ ブリッジ app converter を使うことができます。 詳細については、次を参照してください。 [Centennial プロジェクトで Visual c のランタイムを使用して](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project)と[デスクトップ ブリッジ](/windows/uwp/porting/desktop-to-uwp-root)します。

## <a name="uwp-apps-that-use-cwinrt"></a>C + を使用する UWP アプリ/cli WinRT

C +/cli WinRT は、ヘッダーのみの新しいライブラリに基づく C++ 言語プロジェクション c++ とは異なり、完全に標準の C++ を使用した Windows ランタイムの/cli CX 実装します。 C +/cli WinRT には、非標準の構文または Microsoft 言語拡張機能を使用しないし、高度に最適化された出力を作成する C++ コンパイラを最大限に活用します。 詳細については、次を参照してください。 [C +/cli WinRT](/windows/uwp/cpp-and-winrt-apis)します。 C++ の概要については/cli WinRT とコードのクイック スタートを参照してください。[概要 C +/cli WinRT](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt)します。

## <a name="uwp-apps-that-use-ccx"></a>C + を使用する UWP アプリ/cli CX

|||
|-|-|
|[Visual C++ の言語リファレンス (C++/CX)](../cppcx/visual-c-language-reference-c-cx.md)|C++ を Windows ランタイム Api の使用を簡略化し、例外に基づいているエラー処理を有効にする拡張機能のセットについて説明します。|
|[アプリケーションとライブラリのビルド (C++/CX)](../cppcx/building-apps-and-libraries-c-cx.md)|C ++/CX アプリケーションまたはコンポーネントからアクセスできるスタティック ライブラリと DLL を作成する方法について説明します。|
|[チュートリアル: 作成、UWP「こんにちは, World」のアプリを c++/cli CX](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)|C++ UWP アプリ開発の基本的な概念を説明するチュートリアル/cli CX します。 |
|[Windows ランタイム コンポーネントを作成する c++/cli CX](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)|その他の UWP アプリとコンポーネントが使用できる Dll を作成する方法について説明します。|
|[UWP ゲーム プログラミング](/windows/uwp/gaming/)|DirectX および C++ を使用する方法について説明します/cli/CX をゲームを作成します。|

## <a name="uwp-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>Windows ランタイム C++ テンプレート ライブラリ (WRL) を使用する UWP アプリ

Windows ランタイム C++ テンプレート ライブラリでは、例外のない環境で Windows ランタイムを ISO C のコードからアクセスできる低レベルの COM インターフェイスを提供します。 ほとんどの場合、推奨使用すること C +/cli WinRT または C++/cli CX UWP アプリ開発用 Windows ランタイム C++ テンプレート ライブラリの代わりにします。 Windows ランタイム C++ テンプレート ライブラリについては、次を参照してください。 [Windows ランタイム C++ テンプレート ライブラリ (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)します。

## <a name="see-also"></a>関連項目

[Visual C++](../visual-cpp-in-visual-studio.md)<br/>