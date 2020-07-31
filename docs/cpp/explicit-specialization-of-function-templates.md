---
title: 関数テンプレートの明示的特殊化
ms.date: 11/04/2016
helpviewer_keywords:
- overriding, functions
- function templates, specialization
- explicit specialization of function templates
- declaring functions [C++], specialization of function template
- specialization of function templates
ms.assetid: eb0fcb73-eaed-42a1-9b83-14b055a34bf8
ms.openlocfilehash: 638b5dbca1b3c0c9b9c9c946418ea70354ff6266
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220562"
---
# <a name="explicit-specialization-of-function-templates"></a>関数テンプレートの明示的特殊化

関数テンプレートを使用すると、特定の型のために関数テンプレートの明示的な特殊化 (オーバーライド) を提供することによって、その型の特別な動作を定義できます。 次に例を示します。

```cpp
template<> void MySwap(double a, double b);
```

この宣言により、変数に別の関数を定義でき **`double`** ます。 非テンプレート関数と同様に、標準型変換 (型の変数の昇格など **`float`** **`double`** ) が適用されます。

## <a name="example"></a>例

```cpp
// explicit_specialization.cpp
template<class T> void f(T t)
{
};

// Explicit specialization of f with 'char' with the
// template argument explicitly specified:
//
template<> void f<char>(char c)
{
}

// Explicit specialization of f with 'double' with the
// template argument deduced:
//
template<> void f(double d)
{
}
int main()
{
}
```

## <a name="see-also"></a>関連項目

[関数テンプレート](../cpp/function-templates.md)
