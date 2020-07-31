---
title: コンパイラの警告 (レベル 4) C4459
ms.date: 11/04/2016
f1_keywords:
- C4459
helpviewer_keywords:
- C4459
ms.assetid: ee9f6287-9c70-4b10-82a0-add82a13997f
ms.openlocfilehash: d6d0a802f9f628145fbc5910aca805a5b01b94d2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214374"
---
# <a name="compiler-warning-level-4-c4459"></a>コンパイラの警告 (レベル 4) C4459

> '*identifier*' を宣言すると、グローバル宣言が非表示になります

ローカルスコープの*識別子*の宣言によって、グローバルスコープの同じ名前を持つ*識別子*の宣言が非表示になります。 この警告は、このスコープ内の*識別子*への参照が、グローバルバージョンではなく、ローカルで宣言されたバージョンに解決されることを知らせることができます。これは、意図したものとは異なる場合があります。 一般に、適切なエンジニアリング手法として、グローバル変数の使用を最小限に抑えることをお勧めします。 グローバル名前空間の汚染を最小限に抑えるには、グローバル変数に名前付きの名前空間を使用することをお勧めします。

この警告は、Visual Studio 2015 の Microsoft C++ コンパイラバージョン18.00 で新しく追加されたものです。 コードの移行中に、そのバージョンのコンパイラからの警告を抑制するには、 [/Wv:18](../../build/reference/compiler-option-warning-level.md)コンパイラオプションを使用します。

## <a name="example"></a>例

次の例では、C4459 が生成されます。

```cpp
// C4459_hide.cpp
// compile with: cl /W4 /EHsc C4459_hide.cpp
int global_or_local = 1;

int main() {
    int global_or_local; // warning C4459
    global_or_local = 2;
}
```

この問題を解決する方法の1つは、グローバルの名前空間を作成することですが、ディレクティブを使用して **`using`** その名前空間をスコープにすることはできないため、すべての参照で明確な修飾名を使用する必要があります。

```cpp
// C4459_namespace.cpp
// compile with: cl /W4 /EHsc C4459_namespace.cpp
namespace globals {
    int global_or_local = 1;
}

int main() {
    int global_or_local; // OK
    global_or_local = 2;
    globals::global_or_local = 3;
}
```
