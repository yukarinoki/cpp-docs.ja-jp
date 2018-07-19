---
title: ユニバーサル Windows アプリ (C++) |Microsoft ドキュメント
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
ms.openlocfilehash: 9914e9ac83efcc43ef120259254b65ef4f1e0ee9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891124"
---
# <a name="universal-windows-apps-c"></a>ユニバーサル Windows アプリ (C++)

ユニバーサル Windows プラットフォーム (UWP) アプリは、一連のさまざまなデバイス上のさまざまな画面サイズに合わせて調整されるコンテンツを中心とした、シンプルなユーザー インターフェイスを強調するデザインの原則を具体化します。 XAML マークアップで UI を作成し、ネイティブ C++ で分離コードを作成します。 さらに他の言語で記述された UWP アプリケーションで使用可能なコンポーネント (DLL) を作成できます。 UWP アプリの API サーフェスは、Windows ランタイムでは、さまざまなオペレーティング システムのサービスを提供するための十分に考慮されたライブラリです。

> [!TIP]  
> Windows 10 用 Microsoft ストアを介して展開用の既存のデスクトップ アプリケーションをパッケージ化するのに、ブリッジのデスクトップ アプリのコンバーターを使用できます。 詳細については、次を参照してください。 [100 周年プロジェクトで Visual c のランタイムを使用して](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project)と[デスクトップ ブリッジ](/windows/uwp/porting/desktop-to-uwp-root)です。

## <a name="uwp-apps-that-use-cwinrt"></a>C + を使用する UWP アプリ + WinRT

C + + WinRT 投影である、新しいヘッダーのみライブラリに基づく C++ 言語 c++ とは異なり、完全に標準の C++ で使用される Windows ランタイムの + CX の実装です。 C + + WinRT は非標準の構文または Microsoft 言語拡張機能を使用しないし、高度に最適化の出力を作成する、C++ コンパイラの最大限に活用します。 詳細については、次を参照してください。 [C + + WinRT](/windows/uwp/cpp-and-winrt-apis)です。 C + の概要について + WinRT およびコードのクイック スタートを参照してください。[概要 C + + WinRT](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt)です。

## <a name="uwp-apps-that-use-ccx"></a>UWP アプリを使用して C + + CX

|||
|-|-|
|[Visual C++ の言語リファレンス (C++/CX)](../cppcx/visual-c-language-reference-c-cx.md)|Windows ランタイム Api の C++ の消費量を簡略化し、例外に基づいているエラー処理を有効にする拡張機能のセットについて説明します。|
|[アプリケーションとライブラリのビルド (C++/CX)](../cppcx/building-apps-and-libraries-c-cx.md)|C ++/CX アプリケーションまたはコンポーネントからアクセスできるスタティック ライブラリと DLL を作成する方法について説明します。|
|[チュートリアル: 作成、UWP「こんにちは, World」のアプリの C + + CX](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)|C++ UWP アプリ開発の基本的な概念を説明するチュートリアル + CX です。 |
|[Windows ランタイム コンポーネントを作成する C + + CX](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)|他の UWP アプリやコンポーネントを使用できる Dll を作成する方法について説明します。|
|[UWP ゲームのプログラミング](/windows/uwp/gaming/)|DirectX および C++ を使用する方法について説明 + CX ゲームを作成します。|

## <a name="uwp-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>Windows ランタイム C++ テンプレート ライブラリ (WRL) を使用する UWP アプリ

Windows ランタイム C++ テンプレート ライブラリは、例外を必要としない環境での Windows ランタイムを ISO C のコードからアクセスできる低レベルの COM インターフェイスを提供します。 ほとんどの場合、使用をお勧めする C + + WinRT または C + + CX UWP アプリ開発用 Windows ランタイム C++ テンプレート ライブラリの代わりにします。 Windows ランタイム C++ テンプレート ライブラリの概要については、次を参照してください。 [Windows ランタイム C++ テンプレート ライブラリ (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)です。

## <a name="see-also"></a>関連項目

[Visual C++](../visual-cpp-in-visual-studio.md)<br/>
