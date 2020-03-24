---
title: コンパイラの警告 (レベル 1) C4807
ms.date: 11/04/2016
f1_keywords:
- C4807
helpviewer_keywords:
- C4807
ms.assetid: 089c9f87-fd81-402e-9826-66a8ef1ef1fe
ms.openlocfilehash: 2424d076be0914a68c3227566cb851b7ab64cc0f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175039"
---
# <a name="compiler-warning-level-1-c4807"></a>コンパイラの警告 (レベル 1) C4807

'operation': 'type' 型と 'type' 型の符号付きビットフィールドの混用は安全ではありません。

この警告は、1 ビットの符号付きビットフィールドと `bool` 変数を比較すると、生成されます。 1 ビットの符号付きビットフィールドには、値 -1 または 0 のみを含めることがでるため、 `bool`と比較するのは危険です。 `bool` と 1 ビットの符号なしビットフィールドは `bool` を同じであり、0 または 1 のみを保持できるため、これらを混用しても警告は生成されません。

## <a name="example"></a>例

次の例では C4807 が生成されます。

```cpp
// C4807.cpp
// compile with: /W1
typedef struct bitfield {
   signed mybit : 1;
} mybitfield;

int main() {
   mybitfield bf;
   bool b = true;

   // try..
   // int b = true;

   bf.mybit = -1;
   if (b == bf.mybit) {   // C4807
      b = false;
   }
}
```
