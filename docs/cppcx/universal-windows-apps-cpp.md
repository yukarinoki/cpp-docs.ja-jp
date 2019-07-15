---
title: ユニバーサル Windows アプリ (C++)
ms.date: 03/30/2018
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
ms.openlocfilehash: fbd5366ee52dfe32baef9458a82c16914666699e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392064"
---
# <a name="universal-windows-apps-c"></a>ユニバーサル Windows アプリ (C++)

ユニバーサル Windows プラットフォーム (UWP) は、Windows の最新のプログラミング インターフェイスです。 UWP では、アプリケーションまたはコンポーネントの 1 回の書き込みし、任意の Windows 10 デバイスに展開します。 C++ では、コンポーネントを記述することができ、その他の UWP と互換性のある言語で記述されたアプリケーションで使用できます。

UWP ドキュメントのほとんどは、Windows のコンテンツ ツリーに[ユニバーサル Windows プラットフォーム ドキュメント](/windows/uwp/)します。 最初のチュートリアルがありますも同様のリファレンス ドキュメント。 

新しい UWP アプリとコンポーネントは、お勧めしますを使用すること[C++/WinRT](/windows/uwp/cpp-and-winrt-apis/)、新しい標準 c++ 17 の言語プロジェクションの Windows ランタイム Api です。 C++/WinRT はバージョン 1803 以降から Windows 10 SDK で使用できます。 C++/WinRT はヘッダー ファイル、完全に実装されは最新の Windows API にファースト クラスのアクセス提供するために設計されています。 異なり、 C++/CX 実装します。 C++/WinRT には、非標準の構文または Microsoft 言語拡張機能を使用しないし、高度に最適化された出力を作成する C++ コンパイラを最大限に活用します。 詳細については、次を参照してください。[概要 C++/WinRT](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt)します。

Microsoft Store から展開の既存のデスクトップ アプリケーションをパッケージ化する、デスクトップ ブリッジ app converter を使うことができます。 詳細については、次を参照してください。 [Centennial プロジェクトで Visual c のランタイムを使用して](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project)と[デスクトップ ブリッジ](/windows/uwp/porting/desktop-to-uwp-root)します。

## <a name="uwp-apps-that-use-ccx"></a>C++/CX を使用する UWP アプリ

|||
|-|-|
|[Visual C++ の言語リファレンス (C++/CX)](visual-c-language-reference-c-cx.md)|C++ を Windows ランタイム API の使用を簡略化し、例外に基づいているエラー処理を有効にする拡張機能のセットについて説明します。|
|[アプリケーションとライブラリのビルド (C++/CX)](building-apps-and-libraries-c-cx.md)|C++/CX アプリケーションまたはコンポーネントからアクセスできるスタティック ライブラリと DLL を作成する方法について説明します。|
|[チュートリアル: UWP を作成する「こんにちは, World」のアプリを C++/CX](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)|C++ /CX での UWP アプリ開発の基本概念を紹介するチュートリアル。 |
|[Windows ランタイム コンポーネントを作成する C++/CX](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)|その他の UWP アプリとコンポーネントが使用できる Dll を作成する方法について説明します。|
|[UWP ゲーム プログラミング](/windows/uwp/gaming/)|DirectX と C++/CX を使ってゲームを作成する方法を説明します。|

## <a name="uwp-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>Windows ランタイム C++ テンプレート ライブラリ (WRL) を使用する UWP アプリ

Windows ランタイム C++ テンプレート ライブラリでは、例外のない環境で Windows ランタイムを ISO C のコードからアクセスできる低レベルの COM インターフェイスを提供します。 ほとんどの場合、UWPアプリ開発用indows ランタイム C++ テンプレート ライブラリの代わりに C++/WinRT または C++/CX を使用することを推奨します。 Windows ランタイム C++ テンプレート ライブラリについては、[Windows ランタイム C++ テンプレート ライブラリ (WRL)](wrl/windows-runtime-cpp-template-library-wrl.md)を参照してください。

## <a name="see-also"></a>関連項目

[Visual Studio での C++](../overview/visual-cpp-in-visual-studio.md)<br/>
[C++ でプログラミングする Windows の概要](../windows/overview-of-windows-programming-in-cpp.md)<br/>
