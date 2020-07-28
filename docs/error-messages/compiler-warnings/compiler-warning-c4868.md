---
title: コンパイラの警告 C4868
ms.date: 10/26/2017
f1_keywords:
- C4868
helpviewer_keywords:
- C4868
ms.assetid: fc6aa7e5-34dd-4ec2-88bd-16e430361dc7
ms.openlocfilehash: fe113a948cdf2a6e4b4fcf6b0055fe92d583f004
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220133"
---
# <a name="compiler-warning-level-4-c4868"></a>コンパイラの警告 (レベル 4) C4868

> '_file_(*line_number*) ' コンパイラは、かっこ付き初期化子リストに左から右への評価順序を強制することはできません

かっこ付き初期化子リストの要素は、左から右の順序で評価されます。 コンパイラがこの順序を保証できないケースが2つあります。1つ目は、要素の一部が値によって渡されるオブジェクトである場合です。2つ目は、を使用してコンパイルする場合 `/clr` と、一部の要素がオブジェクトのフィールドまたは配列要素である場合です。 コンパイラは、左から右への評価を保証できない場合、警告 C4868 を出力します。

この警告は、Visual Studio 2015 Update 2 に対して行われたコンパイラ準拠作業の結果として生成されます。 Visual Studio 2015 Update 2 より前にコンパイルされたコードで C4868 が生成されるようになりました。

既定では、この警告はオフに設定されています。 `/Wall`この警告をアクティブにするには、を使用します。

この警告を解決するには、まず、初期化子リストの要素を左から右に評価する必要があるかどうかを検討します。たとえば、要素を評価するときに、順序に依存する副作用が生じる可能性があります。 多くの場合、要素が評価される順序は、観測可能な効果を持ちません。

評価の順序が左から右になる必要がある場合は、代わりに参照によって要素を渡すことができるかどうかを検討してください **`const`** 。 たとえば、次のコードサンプルでは、このような変更によって警告が除去されます。

## <a name="example"></a>例

このサンプルでは、C4868 を生成し、その修正方法を示しています。

```cpp
// C4868.cpp
// compile with: /c /Wall
#include <cstdio>

class HasCopyConstructor
{
public:
    int x;

    HasCopyConstructor(int x): x(x) {}

    HasCopyConstructor(const HasCopyConstructor& h): x(h.x)
    {
        printf("Constructing %d\n", h.x);
    }
};

class TripWarning4868
{
public:
    // note that taking "HasCopyConstructor" parameters by-value will trigger copy-construction.
    TripWarning4868(HasCopyConstructor a, HasCopyConstructor b) {}

    // This variation will not trigger the warning:
    // TripWarning4868(const HasCopyConstructor& a, const HasCopyConstructor& b) {}
};

int main()
{
    HasCopyConstructor a{1};
    HasCopyConstructor b{2};

    // the warning will indicate the below line, the usage of the braced initializer list.
    TripWarning4868 warningOnThisLine{a, b};
};
```
