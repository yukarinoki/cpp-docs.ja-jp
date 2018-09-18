---
title: コンパイラの警告 (レベル 1) C4090 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4090
dev_langs:
- C++
helpviewer_keywords:
- C4090
ms.assetid: baad469d-23d4-45aa-ad9c-305b32d61e9a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4ae34eeb6c87fdb12b07d25c6b6bbcfdd6b5ee21
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024815"
---
# <a name="compiler-warning-level-1-c4090"></a>コンパイラの警告 (レベル 1) C4090

'operation': 異なる 'modifier' 修飾子

操作で使用される変数には、検出されず、コンパイラによって変更されないようにする指定した修飾子が定義されます。 変更しなくても、式がコンパイルされます。

この警告はへのポインターの場合に発生、 **const**または`volatile`を指すとして宣言されていないポインターに項目が割り当てられている**const**または`volatile`。

C プログラムの警告が表示されます。 C++ プログラムでは、コンパイラがエラーを発行: [C2440](../../error-messages/compiler-errors-1/compiler-error-c2440.md)します。

次の例では、C4090 が生成されます。

```
// C4090.c
// compile with: /W1
int *volatile *p;
int *const *q;
int **r;

int main() {
   p = q;   // C4090
   p = r;
   q = p;   // C4090
   q = r;
   r = p;   // C4090
   r = q;   // C4090
}
```