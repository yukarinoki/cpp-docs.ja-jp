---
description: 詳細については、「C++/CX 言語リファレンス」を参照してください。
title: C++/CX 言語リファレンス
ms.date: 09/15/2017
ms.assetid: 3f6abf92-4e5e-4ed8-8e11-f9252380d30a
ms.openlocfilehash: ac72abeb84c656ce0ab9569ad5c944ea61b7d646
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288036"
---
# <a name="ccx-language-reference"></a>C++/CX 言語リファレンス

C++/CX は C++ 言語の一連の拡張機能であり、最新の C++ にできるだけ近い表現形式で Windows アプリと Windows ランタイムコンポーネントを作成できるようにします。 C++/CX を使用して、Windows アプリとコンポーネントをネイティブコードで記述します。このコードは、Visual C#、Visual Basic、JavaScript など、Windows ランタイムをサポートするその他の言語と簡単にやり取りできます。 生の COM インターフェイスまたは非例外的コードへの直接アクセスを必要とするまれなケースでは、 [Windows ランタイム C++ テンプレートライブラリ (WRL)](./wrl/windows-runtime-cpp-template-library-wrl.md)を使用できます。

> [!NOTE]
> **/Cx の代替手段としてC++/WinRT をお勧めします。 [ C++](/windows/uwp/cpp-and-winrt-apis/index)** これは、バージョン1803以降の最新の Windows 10 SDK で使用できる Windows ランタイム Api 向けの新しい標準 C++ 17 言語のプロジェクションです。 C++/WinRT は、完全にヘッダーファイルに実装され、最新の Windows API へのファーストクラスのアクセスを提供するように設計されています。
>
> C++/WinRT では、標準に準拠した C++ 17 コンパイラを使用して Windows ランタイム Api を使用し、作成することができます。 C++/WinRT は通常、より優れたパフォーマンスを発揮し、Windows ランタイムの他の言語オプションよりも小さなバイナリを生成します。 C++/CX と WRL は引き続きサポートされますが、新しいアプリケーションでは C++/WinRT を使用することを強くお勧めします。 詳細については、「[C++/WinRT](/windows/uwp/cpp-and-winrt-apis/index)」を参照してください。

C++/CX を使用すると、次のものを作成できます。

- XAML を使用してユーザーインターフェイスを定義し、ネイティブスタックを使用する C++ ユニバーサル Windows プラットフォーム (UWP) アプリ。 詳細については、「 [C++ (UWP) での "hello world" アプリの作成](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)」を参照してください。

- C++ は、JavaScript ベースの Windows アプリで使用できるコンポーネントを Windows ランタイムします。 詳細については、「 [Creating Windows Runtime Components in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)」を参照してください。

- Windows DirectX ゲームやグラフィックス処理の多いアプリ。 詳細については、「 [DirectX を使用した簡単な UWP ゲームの作成](/windows/uwp/gaming/tutorial--create-your-first-uwp-directx-game)」を参照してください。

## <a name="related-articles"></a>関連記事

| Link | 説明 |
|--|--|
| [クイックリファレンス](../cppcx/quick-reference-c-cx.md) | C++/CX のキーワードと演算子の表。 |
| [型システム](../cppcx/type-system-c-cx.md) | C++/CX の基本型とプログラミング構成要素について説明し、C++/CX を使用して Windows ランタイム型を使用および作成する方法について説明します。 |
| [アプリとライブラリのビルド](../cppcx/building-apps-and-libraries-c-cx.md) | IDE を使用してアプリを構築し、スタティックライブラリおよび Dll にリンクする方法について説明します。 |
| [他の言語との相互運用](../cppcx/interoperating-with-other-languages-c-cx.md) | C++/CX を使用して記述されたコンポーネントを、JavaScript、マネージ言語、または Windows ランタイム C++ テンプレートライブラリで記述されたコンポーネントで使用する方法について説明します。 |
| [スレッド処理とマーシャリング](../cppcx/threading-and-marshaling-c-cx.md) | 作成するコンポーネントのスレッドとマーシャリングの動作を指定する方法について説明します。 |
| [名前空間のリファレンス](../cppcx/namespaces-reference-c-cx.md) | 既定の名前空間、Platform 名前空間、Platform::Collections、および関連する名前空間の参照ドキュメント。 |
| [ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) | Windows ランタイム アプリでは使用できない CRT 関数の一覧を示します。 |
| [Windows 10 アプリの概要](/windows/uwp/get-started/) | Windows 10 アプリについての全般的な概要と、詳細情報へのリンクがあります。 |
| [C++/CX パート 0/ \[ n \] : 概要](https://devblogs.microsoft.com/cppblog/ccx-part-0-of-n-an-introduction/)<br /><br />[C++/CX パート 1/ \[ n \] : 単純なクラス](https://devblogs.microsoft.com/cppblog/ccx-part-1-of-n-a-simple-class/)<br /><br />[C++/CX パート 2/ \[ n \] : 摩耗帽子](https://devblogs.microsoft.com/cppblog/ccx-part-2-of-n-types-that-wear-hats/)<br /><br />[C++/CX パート 3/ \[ n \] : 構築中](https://devblogs.microsoft.com/cppblog/ccx-part-3-of-n-under-construction/)<br /><br />[C++/CX パート 4 of \[ n \] : 静的メンバー関数](https://devblogs.microsoft.com/cppblog/ccx-part-4-of-n-static-member-functions/)| C++/CX の入門ブログシリーズです。 |
