---
title: マクロと C++
ms.date: 11/04/2016
helpviewer_keywords:
- macros, C++
- macros
ms.assetid: 83a344c1-73c9-4ace-8b93-cccfb62c6133
ms.openlocfilehash: cd5d1237bc025cceb25cc290509b929b595a215f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499893"
---
# <a name="macros-and-c"></a>マクロと C++
C++ にはいくつかの新機能がありますが、その一部は ANSI C プリプロセッサが提供する機能に代替します。 これらの新機能によって、次のように言語のタイプ セーフと予測可能性が向上します。

- C++ では、オブジェクトの宣言として**const**定数式で使用できます。 これによりプログラム内で、型と値の情報を持つ定数と、デバッガーによって記号で表示できる列挙体を宣言できます。 これに比べて、プリプロセッサの `#define` ディレクティブを使用して定数を定義する方法は、あまり正確ではありません。 記憶域が割り当てられていません、 **const**オブジェクトのアドレスを取得する式がプログラムに存在しない限り、します。

- C++ のインライン関数の機能が、関数型マクロに代わって提供されています。 マクロよりもインライン関数を使用することの利点は次のとおりです。

    - インライン関数はタイプ セーフです。 インライン関数には、通常の関数と同じ型チェックが実行されます。 マクロは、タイプ セーフではありません。

    - インライン関数では、副作用のある引数の処理が修正されます。 インライン関数は、関数本体を入力する前に、引数として渡された式を評価します。 したがって、副作用のある式が安全でない状態のまま使用される可能性はありません。

インライン関数の詳細については、次を参照してください。 [inline、_ _inline、 \__forceinline](../cpp/inline-functions-cpp.md)します。

下位互換性を維持するため、ANSI C と以前の C++ 仕様にあるすべてのプリプロセッサ機能は Microsoft C++ で保持されています。

## <a name="see-also"></a>関連項目

[定義済みマクロ](../preprocessor/predefined-macros.md)<br/>
[マクロ (C/C++)](../preprocessor/macros-c-cpp.md)