---
description: '詳細情報: コンパイラの警告 (レベル 4) C4366'
title: コンパイラの警告 (レベル 4) C4366
ms.date: 11/04/2016
f1_keywords:
- C4366
helpviewer_keywords:
- C4366
ms.assetid: 65d2942f-3741-42f4-adf2-4920d5a055ca
ms.openlocfilehash: 9fa703d64ca48090d3bf6c2f5d9e21668d9acd71
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330602"
---
# <a name="compiler-warning-level-4-c4366"></a>コンパイラの警告 (レベル 4) C4366

単項演算子 ' operator ' の結果は、整列されていない可能性があります。

パッキングのために構造体のメンバーが整列されていない場合、そのメンバーのアドレスがアラインされたポインターに割り当てられると、コンパイラは警告を出します。 既定では、すべてのポインターがアラインされます。

C4366 を解決するには、構造体の配置を変更するか、 [__unaligned](../../cpp/unaligned.md) キーワードを使用してポインターを宣言します。

詳細については、「__unaligned と [パック](../../preprocessor/pack.md)」を参照してください。

## <a name="example"></a>例

次の例では、C4366 が生成されます。

```cpp
// C4366.cpp
// compile with: /W4 /c
// processor: IPF x64
#pragma pack(1)
struct X {
   short s1;
   int s2;
};

int main() {
   X x;
   short * ps1 = &x.s1;   // OK
   int * ps2 = &x.s2;   // C4366
}
```
