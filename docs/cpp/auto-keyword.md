---
title: auto キーワード
ms.date: 05/07/2019
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
ms.openlocfilehash: a695c33ab55601bb8d81b00f963646f6a48f09d5
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222251"
---
# <a name="auto-keyword"></a>auto キーワード

**auto**キーワードは宣言指定子。 ただし、C++ 標準ではこのキーワードの元の意味と変更後の意味が定義されます。 Visual Studio 2010 では、前に、**auto**キーワードで変数の宣言、*auto*ストレージ クラス、つまり、ローカルな有効期間を持つ変数です。 Visual Studio 2010 以降で、**auto**キーワードは、その宣言の初期化式から推測される型の変数を宣言します。 [/Zc:auto&#91;-&#93; ](../build/reference/zc-auto-deduce-variable-type.md)コンパイラ オプションの意味を制御する、**auto**キーワード。

## <a name="syntax"></a>構文

```cpp
auto declarator ;
auto declarator initializer;
```

## <a name="remarks"></a>Remarks

定義、**auto**C プログラミング言語ではなく、C++ のプログラミング言語でキーワードを変更します。

次のトピックについて説明します、**auto**キーワードと、対応するコンパイラ オプション。

- [自動](../cpp/auto-cpp.md)の新しい定義を説明します、**auto**キーワード。

- [/Zc:auto (変数の型の推測)](../build/reference/zc-auto-deduce-variable-type.md)のどの定義をコンパイラに指示するコンパイラ オプションについて説明します、**auto**キーワードを使用します。

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)