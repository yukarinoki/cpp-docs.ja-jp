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
ms.openlocfilehash: c9d77cef790bdd0a65651ffb7246e685175482b1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179992"
---
# <a name="explicit-specialization-of-function-templates"></a>関数テンプレートの明示的特殊化

関数テンプレートを使用すると、特定の型のために関数テンプレートの明示的な特殊化 (オーバーライド) を提供することによって、その型の特別な動作を定義できます。 次に例を示します。

```cpp
template<> void MySwap(double a, double b);
```

この宣言により、 **double**変数に対して別の関数を定義できます。 非テンプレート関数と同様に、標準型変換 ( **float**型の変数の昇格**など) が**適用されます。

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

## <a name="see-also"></a>参照

[関数テンプレート](../cpp/function-templates.md)
