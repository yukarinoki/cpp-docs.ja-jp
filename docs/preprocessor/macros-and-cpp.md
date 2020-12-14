---
description: 詳細については、「マクロと C++」を参照してください。
title: マクロと C++
ms.date: 08/29/2019
helpviewer_keywords:
- macros, C++
- macros
ms.assetid: 83a344c1-73c9-4ace-8b93-cccfb62c6133
ms.openlocfilehash: 2ec4db1e36bf18c23567c8c513bdc5e15ec613a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333430"
---
# <a name="macros-and-c"></a>マクロと C++

C++ には新しい機能が用意されており、その中には ANSI C プリプロセッサによって提供される機能を代わりするものがあります。 これらの新機能によって、次のように言語のタイプ セーフと予測可能性が向上します。

- C++ では、として宣言されたオブジェクトを **`const`** 定数式で使用できます。 プログラムは、型と値の情報を持つ定数を宣言できます。 デバッガーで参照できる列挙を宣言できます。 プリプロセッサディレクティブを使用して定数を定義する場合は、 `#define` 厳密ではなく、タイプセーフではありません。 **`const`** オブジェクトのアドレスを受け取る式がプログラムに含まれていない限り、ストレージは割り当てられません。

- C++ のインライン関数の機能が、関数型マクロに代わって提供されています。 マクロよりもインライン関数を使用することの利点は次のとおりです。

  - インライン関数はタイプ セーフです。 インライン関数には、通常の関数と同じ型チェックが実行されます。 マクロはタイプセーフではありません。

  - インライン関数では、副作用のある引数の処理が修正されます。 インライン関数は、関数本体を入力する前に、引数として指定された式を評価します。 したがって、副作用のある式は安全でない可能性があります。

インライン関数の詳細については、「 [inline、__inline、 \_ _forceinline](../cpp/inline-functions-cpp.md)」を参照してください。

下位互換性を維持するため、ANSI C と以前の C++ 仕様にあるすべてのプリプロセッサ機能は Microsoft C++ で保持されています。

## <a name="see-also"></a>関連項目

[定義済みマクロ](../preprocessor/predefined-macros.md)\
[マクロ (C/C++)](../preprocessor/macros-c-cpp.md)
