---
title: コンパイラの警告 (レベル 1) C4305
ms.date: 01/17/2018
f1_keywords:
- C4305
helpviewer_keywords:
- C4305
ms.openlocfilehash: 567442bc48487e4f7d1f905f871d15f913646e87
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233289"
---
# <a name="compiler-warning-level-1-c4305"></a>コンパイラの警告 (レベル 1) C4305

> '*context*': ' type1 *' から '**type1*' への切り捨て

## <a name="remarks"></a>解説

この警告は、値が初期化時に小さい型に変換されるか、コンストラクター引数として変換されると、情報が失われる場合に発行されます。

## <a name="example"></a>例

このサンプルでは、次の2つの方法でこの警告が表示されます。

```cpp
// C4305.cpp
// Compile by using: cl /EHsc /W4 C4305.cpp

struct item
{
    item(float) {}
};

int main()
{
    float f = 2.71828;          // C4305 'initializing'
    item i(3.14159);            // C4305 'argument'
    return static_cast<int>(f);
}
```

この問題を解決するには、正しい型の値を使用してを初期化するか、適切な型への明示的なキャストを使用します。 たとえば、 **`float`** (浮動小数点リテラルの既定の型) ではなく 2.71828 f などのリテラルを使用して **`double`** 変数を初期化する **`float`** か、引数を受け取るコンストラクターに渡すことが **`float`** できます。
