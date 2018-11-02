---
title: auto キーワード
ms.date: 11/04/2016
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
ms.openlocfilehash: 3477bd5033fac5b69733db5d6095c1317aac42ee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607689"
---
# <a name="auto-keyword"></a>auto キーワード

**自動**キーワードは宣言指定子。 ただし、C++ 標準ではこのキーワードの元の意味と変更後の意味が定義されます。 Visual C 2010 では、前に、**自動**キーワードで変数の宣言、*自動*ストレージ クラス、つまり、ローカルな有効期間を持つ変数です。 Visual C 2010 では、以降、**自動**キーワードは、その宣言の初期化式から推測される型の変数を宣言します。 [/Zc:auto&#91;-&#93; ](../build/reference/zc-auto-deduce-variable-type.md)コンパイラ オプションの意味を制御する、**自動**キーワード。

## <a name="syntax"></a>構文

```cpp
auto declarator ;
auto declarator initializer;
```

## <a name="remarks"></a>Remarks

定義、**自動**C プログラミング言語ではなく、C++ のプログラミング言語でキーワードを変更します。

次のトピックについて説明します、**自動**キーワードと、対応するコンパイラ オプション。

- [自動](../cpp/auto-cpp.md)の新しい定義を説明します、**自動**キーワード。

- [/Zc:auto (変数の型の推測)](../build/reference/zc-auto-deduce-variable-type.md)のどの定義をコンパイラに指示するコンパイラ オプションについて説明します、**自動**キーワードを使用します。

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)