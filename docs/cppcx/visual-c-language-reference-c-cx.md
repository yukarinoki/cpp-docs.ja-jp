---
title: Visual C++ の言語リファレンス (C++/CX)
ms.date: 09/15/2017
ms.assetid: 3f6abf92-4e5e-4ed8-8e11-f9252380d30a
ms.openlocfilehash: ce0272499b653b9077a891e39e9b29797e7e051d
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328416"
---
# <a name="visual-c-language-reference-ccx"></a>Visual C++ の言語リファレンス (C++/CX)

C + + CX は Windows アプリと C++ の最新にできるだけ近い表現での Windows ランタイム コンポーネントの作成を有効にする C++ 言語への拡張のセットです。 C++/cli/CX を簡単に Visual c#、Visual Basic、および JavaScript と対話するネイティブ コードと Windows ランタイムをサポートするその他の言語で Windows アプリやコンポーネントを記述します。 生の COM インターフェイスまたは非例外的なコードに直接アクセスを必要とするこれらのまれなケースで使用することができます、 [Windows ランタイム C++ テンプレート ライブラリ (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)します。

> [!NOTE]
> **[C +/cli WinRT](/windows/uwp/cpp-and-winrt-apis/index)は、推奨される代替 C + + CX**します。 新しい、標準的な c++ 17 の言語プロジェクションの Windows ランタイム Api をバージョン 1803 以降から最新の Windows 10 SDK で使用できるになります。 C +/cli WinRT がヘッダー ファイルで完全に実装し、最新の Windows API に最上級アクセスを提供するように設計します。
>
> C++/cli WinRT、両方を使用して標準に準拠した c++ 17 コンパイラを使用して Windows ランタイム Api を作成します。 C +/cli WinRT は通常、パフォーマンスが向上し、Windows ランタイムの他の言語オプションよりも小さいバイナリを生成します。 C + をサポートするために引き続き/cli CX および WRL、C + 新しいアプリケーションを使用するを強くお勧めしますが、/cli WinRT します。 詳細については、次を参照してください。 [C +/cli WinRT](/windows/uwp/cpp-and-winrt-apis/index)します。

C + を使用して/cli CX を作成できます。

- ユーザーを定義する XAML を使用する C++ ユニバーサル Windows プラットフォーム (UWP) アプリでは、インターフェイスし、ネイティブ スタックを使用します。 詳細については、次を参照してください。 ["hello world"アプリを作成するには、C++ (UWP) で](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)します。

- JavaScript ベースの Windows アプリで使用できる C++ Windows ランタイム コンポーネントです。 詳細については、「 [Creating Windows Runtime Components in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)」を参照してください。

- Windows DirectX ゲームやグラフィックス処理の多いアプリ。 詳細については、次を参照してください。 [UWP の簡単なゲームを DirectX を使った作成](/windows/uwp/gaming/tutorial--create-your-first-uwp-directx-game)です。

## <a name="related-articles"></a>関連記事

|||
|-|-|
|[クイック リファレンス](../cppcx/quick-reference-c-cx.md)|テーブルのキーワードと演算子の C + + CX します。|
|[型システム](../cppcx/type-system-c-cx.md)|説明する基本的な C +/cli CX 型と、プログラミング構成要素と C + を利用する方法/cli/CX を使用して、Windows ランタイム型を作成します。|
|[アプリの構築とライブラリ](../cppcx/building-apps-and-libraries-c-cx.md)|IDE を使用してアプリを作成し、スタティック ライブラリと Dll にリンクする方法について説明します。|
|[その他の言語との相互運用](../cppcx/interoperating-with-other-languages-c-cx.md)|について説明しますどの C + を使用して作成されたコンポーネント/cli CX を使用する、JavaScript で記述されたコンポーネントを管理している言語、または Windows ランタイム C++ テンプレート ライブラリです。|
|[スレッドとマーシャ リング](../cppcx/threading-and-marshaling-c-cx.md)|作成するコンポーネントのスレッドとマーシャリングの動作を指定する方法について説明します。|
|[名前空間参照](../cppcx/namespaces-reference-c-cx.md)|既定の名前空間、Platform 名前空間、Platform::Collections、および関連する名前空間の参照ドキュメント。|
|[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)|Windows ランタイム アプリでは使用できない CRT 関数の一覧を示します。|
|[Windows 10 アプリに関するハウツー ガイド](https://msdn.microsoft.com/library/windows/apps/xaml/mt244352.aspx)|Windows 10 アプリについての全般的な概要と、詳細情報へのリンクがあります。|
|[C + +/CX Part 0 of \[n\]:概要](https://blogs.msdn.microsoft.com/vcblog/2012/08/29/ccx-part-0-of-n-an-introduction/)<br /><br />[C + +/CX Part 1 of \[n\]:単純なクラス](https://blogs.msdn.microsoft.com/vcblog/2012/09/05/ccx-part-1-of-n-a-simple-class/)<br /><br />[C + +/CX Part 2 of \[n\]:ハット記号が型](https://blogs.msdn.microsoft.com/vcblog/2012/09/17/ccx-part-2-of-n-types-that-wear-hats/)<br /><br />[C + +/CX Part 3 of \[n\]:工事中](https://blogs.msdn.microsoft.com/vcblog/2012/10/05/ccx-part-3-of-n-under-construction/)<br /><br />[C + +/CX Part 4 of \[n\]:静的メンバー関数](https://blogs.msdn.microsoft.com/vcblog/2012/10/19/ccx-part-4-of-n-static-member-functions/)|入門の Visual C ブログ シリーズで C + + CX します。|
