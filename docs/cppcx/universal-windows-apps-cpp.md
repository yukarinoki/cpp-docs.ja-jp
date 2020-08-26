---
title: ユニバーサル Windows アプリ (C++)
ms.date: 03/30/2018
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
ms.topic: overview
ms.openlocfilehash: 45d02a5ab923ee46da97d78a1e5ceb2f4313352a
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841675"
---
# <a name="universal-windows-apps-c"></a>ユニバーサル Windows アプリ (C++)

ユニバーサル Windows プラットフォーム (UWP) は、Windows の最新のプログラミングインターフェイスです。 UWP では、アプリケーションまたはコンポーネントを1回記述し、任意の Windows 10 デバイスにデプロイします。 C++ でコンポーネントを記述することができ、他の UWP 互換言語で記述されたアプリケーションはそれを使用できます。

UWP ドキュメントのほとんどは、 [ユニバーサル Windows プラットフォームのドキュメント](/windows/uwp/)にある Windows コンテンツツリーに含まれています。 ここでは、最初のチュートリアルとリファレンスドキュメントを紹介します。

新しい UWP アプリとコンポーネントの場合は、Windows ランタイム Api 向けの新しい標準 C++ 17 言語プロジェクションである [c++/WinRT](/windows/uwp/cpp-and-winrt-apis/)を使用することをお勧めします。 C++/WinRT は、Windows 10 SDK のバージョン 1803 以降で使用できます。 C++/WinRT は、全体がヘッダー ファイル内に実装され、最新の Windows API に対する最高級のアクセスを提供するように設計されています。 C++/CX の実装とは異なり、C++/WinRT では、非標準の構文または Microsoft 言語拡張を使用しないため、高度に最適化された出力を作成するために C++ コンパイラを最大限に活用できます。 詳細については、「 [C++/WinRT の概要](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt)」を参照してください。

Desktop Bridge app converter を使用して、既存のデスクトップアプリケーションをパッケージ化して、Microsoft Store でデプロイできます。 詳細については、「Centennial プロジェクトと[デスクトップブリッジ](/windows/uwp/porting/desktop-to-uwp-root)[での Visual C++ ランタイムの使用](https://devblogs.microsoft.com/cppblog/using-visual-c-runtime-in-centennial-project/)」を参照してください。

## <a name="uwp-apps-that-use-ccx"></a>C++/CX を使用する UWP アプリ

[C++/CX 言語リファレンス](visual-c-language-reference-c-cx.md)\
Windows ランタイム Api の C++ の使用を簡略化し、例外に基づくエラー処理を可能にする一連の拡張機能について説明します。

[アプリとライブラリのビルド (C++/CX)](building-apps-and-libraries-c-cx.md)\
C ++/CX アプリケーションまたはコンポーネントからアクセスできるスタティック ライブラリと DLL を作成する方法について説明します。

[チュートリアル: C++/CX で UWP の "Hello, World" アプリを作成する](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)\
C++/CX での UWP アプリ開発の基本的な概念を紹介するチュートリアルです。

[C++/CX での Windows ランタイムコンポーネントの作成](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)\
他の UWP アプリおよびコンポーネントが使用できる Dll を作成する方法について説明します。

[UWP ゲームのプログラミング](/windows/uwp/gaming/)\
DirectX および C++/CX を使用してゲームを作成する方法について説明します。

## <a name="uwp-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>Windows ランタイム C++ テンプレートライブラリ (WRL) を使用する UWP アプリ

Windows ランタイム C++ テンプレートライブラリは、ISO C++ コードが例外のない環境で Windows ランタイムにアクセスできるようにする、下位レベルの COM インターフェイスを提供します。 多くの場合、UWP アプリの開発には、Windows ランタイム C++ テンプレートライブラリではなく、C++/WinRT または C++/CX を使用することをお勧めします。 Windows ランタイム C++ テンプレートライブラリの詳細については、「 [Windows ランタイム C++ テンプレートライブラリ (WRL)](wrl/windows-runtime-cpp-template-library-wrl.md)」を参照してください。

## <a name="see-also"></a>関連項目

[Visual Studio での C++](../overview/visual-cpp-in-visual-studio.md)<br/>
[C++ での Windows プログラミングの概要](../windows/overview-of-windows-programming-in-cpp.md)<br/>
