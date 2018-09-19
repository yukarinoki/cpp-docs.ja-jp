---
title: コンパイラ エラー C2433 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2433
dev_langs:
- C++
helpviewer_keywords:
- C2433
ms.assetid: 7079fedd-6059-4125-82ef-ebe275f1f9d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 081e63c83909319164a2903d8277a0b26a1e6901
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46059954"
---
# <a name="compiler-error-c2433"></a>コンパイラ エラー C2433

'identifier': 'modifier' はデータの宣言で許可されていません

`friend`、 `virtual`、および`inline`データの宣言に修飾子は使用できません。

## <a name="example"></a>例

次の例では、C2433 が生成されます。

```
// C2433.cpp
class C{};

int main() {
   inline C c;   // C2433
}
```