---
title: コンパイラ エラー C2669 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2669
dev_langs:
- C++
helpviewer_keywords:
- C2669
ms.assetid: f9cb8111-bcdc-484b-a863-2c42e15a0496
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 04363816e69dd560acc0497128f13d92c9878005
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050698"
---
# <a name="compiler-error-c2669"></a>コンパイラ エラー C2669

メンバー関数は無名共用体では使用できません。

[無名共用体](../../cpp/unions.md#anonymous_unions)メンバー関数を含めることはできません。

## <a name="example"></a>例

次の例では、C2669 が生成されます。

```cpp
// C2669.cpp
struct X {
   union {
      int i;
      void f() {   // C2669, remove function
         i = 0;
      }
   };
};
```
