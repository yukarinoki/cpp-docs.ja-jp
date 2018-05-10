---
title: Visual C 言語リファレンス (C + + CX) |Microsoft ドキュメント
ms.custom: ''
ms.date: 09/15/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 3f6abf92-4e5e-4ed8-8e11-f9252380d30a
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2b251a89eee456905fae1e2096a74362fc6c44ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="visual-c-language-reference-ccx"></a>Visual C++ の言語リファレンス (C++/CX)

C + + CX は、Windows アプリ、および C++ の最新にできるだけ近い表現での Windows ランタイム コンポーネントの作成を有効にする、C++ 言語への拡張のセット。 使用する C + +/CX Windows アプリやコンポーネントを簡単にやり取り Visual c#、Visual Basic、および JavaScript をネイティブ コードと Windows ランタイムをサポートするその他の言語で記述をします。 生の COM インターフェイスまたは非例外コードに直接アクセスを必要とするそれらのまれなケースで使用できます、 [Windows ランタイム C++ テンプレート ライブラリ (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)です。

> [!NOTE]
> C + + WinRT 投影である新しい、標準 c++ 17 の言語の Windows ランタイム Api。 最新の Windows 10 SDK 以降のバージョン 1803 で使用します。 C + + WinRT がヘッダー ファイルの完全に実装され、最新の Windows API にファースト クラスのアクセスを提供するように設計します。

> C + + WinRT、両方を使用してその標準に準拠した c++ 17 コンパイラを使用して Windows ランタイム Api を作成します。 C + + WinRT は通常パフォーマンスが向上し、Windows ランタイムの他の言語オプションよりも小さいバイナリを生成します。 C + をサポートするために引き続き +/CX および WRL、C + 新しいアプリケーションに使用することを強く勧めが + WinRT です。 詳細については、次を参照してください。 [C + + WinRT](https://docs.microsoft.com/windows/uwp/cpp-and-winrt-apis/index)です。


による C + + CX を作成できます。

- ユーザーを定義する XAML を使用する C++ ユニバーサル Windows プラットフォーム (UWP) アプリは、インターフェイスし、ネイティブ スタックを使用します。 詳細については、次を参照してください。 [C++ (UWP) に"hello world"アプリを作成する](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)です。

- JavaScript ベースの Windows アプリで利用できる C++ の Windows ランタイム コンポーネントです。 詳細については、次を参照してください。 [C++ での Windows ランタイム コンポーネントの作成](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)です。

- Windows DirectX ゲームやグラフィックス処理の多いアプリ。 詳細については、次を参照してください。 [DirectX で UWP の簡単なゲームを作成する](/windows/uwp/gaming/tutorial--create-your-first-metro-style-directx-game)です。

## <a name="related-articles"></a>関連記事

|||
|-|-|
|[クイック リファレンス](../cppcx/quick-reference-c-cx.md)|テーブルのキーワードと演算子の C + + CX です。|
|[型システム](../cppcx/type-system-c-cx.md)|説明基本的な C + + CX 型とプログラミング構成要素、および C + を利用する方法 +/CX を使用して、Windows ランタイム型を作成します。|
|[アプリのビルドとライブラリ](../cppcx/building-apps-and-libraries-c-cx.md)|IDE を使用してアプリケーションをビルドし、スタティック ライブラリおよび DLL にリンクする方法について説明します。|
|[その他の言語と相互運用](../cppcx/interoperating-with-other-languages-c-cx.md)|について説明方法 C + を使用して記述されたコンポーネント + CX を使用できる JavaScript で記述されたコンポーネントとマネージ言語、または[!INCLUDE[cppwrl](../cppcx/includes/cppwrl-md.md)]です。|
|[スレッドとマーシャ リング](../cppcx/threading-and-marshaling-c-cx.md)|作成するコンポーネントのスレッドとマーシャリングの動作を指定する方法について説明します。|
|[名前空間参照](../cppcx/namespaces-reference-c-cx.md)|既定の名前空間、Platform 名前空間、Platform::Collections、および関連する名前空間の参照ドキュメント。|
|[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)|Windows ランタイム アプリでは使用できない CRT 関数の一覧を示します。|
|[Windows 10 アプリに関するハウツー ガイド](http://msdn.microsoft.com/library/windows/apps/xaml/mt244352.aspx)|Windows 10 アプリについての全般的な概要と、詳細情報へのリンクがあります。|
|[C + +/CX Part 0 of \[n\]: 概要](https://blogs.msdn.microsoft.com/vcblog/2012/08/29/ccx-part-0-of-n-an-introduction/)<br /><br />[C + +/CX パート 1 \[n\]: 単純なクラス](https://blogs.msdn.microsoft.com/vcblog/2012/09/05/ccx-part-1-of-n-a-simple-class/)<br /><br />[C + +/CX Part 2 of \[n\]: ハット記号が付いた型](https://blogs.msdn.microsoft.com/vcblog/2012/09/17/ccx-part-2-of-n-types-that-wear-hats/)<br /><br />[C + +/CX Part 3 of \[n\]: Under Construction](https://blogs.msdn.microsoft.com/vcblog/2012/10/05/ccx-part-3-of-n-under-construction/)<br /><br />[C + +/CX Part 4 of \[n\]: 静的メンバー関数](https://blogs.msdn.microsoft.com/vcblog/2012/10/19/ccx-part-4-of-n-static-member-functions/)|入門の Visual C ブログ シリーズ C + + CX です。|
