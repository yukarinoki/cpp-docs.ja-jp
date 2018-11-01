---
title: 混合、純粋、および検証可能な機能の比較 (C +/cli CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- safe assemblies [C++], vs. pure
- mixed assemblies [C++], vs. pure
- safe assemblies [C++], vs. mixed
- pure MSIL [C++]
- verifiable assemblies [C++]
- pure MSIL [C++], vs. safe
- pure MSIL [C++], vs. mixed
- pure MSIL [C++], compared to mixed and safe
- verifiable assemblies [C++], vs. mixed
- mixed assemblies [C++], vs. safe
- verifiable assemblies [C++], vs. pure
- pure assemblies [C++]
- safe assemblies [C++]
- mixed assemblies [C++]
ms.assetid: 3f7a82ba-0e69-4927-ba0c-fbc3160e4394
ms.openlocfilehash: 81fcf986ee68f5f8f64c8070bb992fa1cda1683b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482073"
---
# <a name="mixed-pure-and-verifiable-feature-comparison-ccli"></a>混合、純粋、および検証可能な機能の比較 (C +/cli CLI)

このトピックでは、別の機能を比較 **/clr**コンパイル モード。 詳細については、「[/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。

> [!IMPORTANT]
> **/Clr: 純粋な**と **/clr:safe**コンパイラ オプションは Visual Studio 2015 で非推奨とされ、Visual Studio 2017 でサポートされていません。

## <a name="feature-comparison"></a>機能の比較

|機能|混合 (/clr)|純粋 (/clr:pure)|安全な (//clr:safe)|関連情報|
|-------------|---------------------|-------------------------|-------------------------|-------------------------|
|CRT ライブラリ|サポートされています|非推奨||[カテゴリ別ユニバーサル C ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)|
|MFC/ATL|サポートされています|||[MFC デスクトップ アプリケーション](../mfc/mfc-desktop-applications.md) &#124; [クラスの概要](../atl/atl-class-overview.md)|
|アンマネージ関数|サポートされています|||[混在 (ネイティブおよびマネージド) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)|
|非管理対象データ|サポートされています|非推奨||[純粋なコードと検証可能なコード (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)|
|アンマネージ関数から呼び出し可能|サポートされています||||
|アンマネージ関数の呼び出しをサポートしています|サポートされています|非推奨|非推奨|[C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)|
|リフレクションをサポートしています|Dll のみ|非推奨|非推奨|[リフレクションの問題 (C++/CLI)](../dotnet/reflection-cpp-cli.md)|

## <a name="see-also"></a>関連項目

- [純粋なコードと検証可能なコード (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)