---
title: コンパイラ エラー C2868
ms.date: 11/04/2016
f1_keywords:
- C2868
helpviewer_keywords:
- C2868
ms.assetid: 6ff5837b-e66d-44d1-9d17-80af35e08d08
ms.openlocfilehash: 0cbcf7dc80aedc554594f88992059f98b7091c21
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201638"
---
# <a name="compiler-error-c2868"></a>コンパイラ エラー C2868

> '*identifier*': using 宣言の構文が正しくありません。修飾名が必要です

[Using 宣言](../../cpp/using-declaration.md)には、*修飾名*、スコープ演算子 (`::`) で区切られた名前空間、クラス、または列挙型の名前が識別子名で終わる必要があります。 単一のスコープ解決演算子を使用して、グローバル名前空間から名前を導入することができます。

## <a name="example"></a>例

次の例では、C2868 を生成し、正しい使用法も示しています。

```cpp
// C2868.cpp
class X {
public:
   int i;
};

class Y : X {
public:
   using X::i;   // OK
};

int main() {
   using X;   // C2868
}
```
