---
title: コンパイラの警告 (レベル 3) C4316
ms.date: 11/04/2016
f1_keywords:
- C4316
helpviewer_keywords:
- C4316
ms.assetid: 10371f01-aeb8-40ac-a290-59e63efa5ad4
ms.openlocfilehash: 0d920cb3dc967854d1a507d06ce31fde6a670434
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198849"
---
# <a name="compiler-warning-level-3-c4316"></a>コンパイラの警告 (レベル 3) C4316

ヒープで割り当てられているオブジェクトが、この型にアラインされていない可能性があります。

`operator new` を使用して割り当てられたオブジェクトがオーバーアラインされている場合は、このオブジェクトにアラインメントが指定されていない可能性があります。 配置された割り当てルーチン ( [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md)や[_aligned_free](../../c-runtime-library/reference/aligned-free.md)など) を使用するように、オーバーアラされた型に対して[operator new](../../c-runtime-library/operator-new-crt.md)と[operator delete](../../c-runtime-library/operator-delete-crt.md)をオーバーライドします。 次の例では、C4316 が生成されます。

```cpp
// C4316.cpp
// Test: cl /W3 /c C4316.cpp

__declspec(align(32)) struct S {}; // C4324

int main() {
    new S; // C4316
}
```
