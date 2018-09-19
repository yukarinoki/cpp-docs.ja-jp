---
title: コンパイラ エラー C3748 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3748
dev_langs:
- C++
helpviewer_keywords:
- C3748
ms.assetid: 6fe71a0a-dd93-4ce6-9729-b9616360cf34
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 31b2d0434ec48f0c1d7ecf767ce2746e2c603401
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116854"
---
# <a name="compiler-error-c3748"></a>コンパイラ エラー C3748

'interface': マネージ インターフェイスは、イベントを発生しない可能性があります

[_ _Event](../../cpp/event.md)インターフェイス内でキーワードは使用できません。

次の例では、C3748 が生成されます。

```
// C3748.cpp
__interface I {
// try the following line instead
// struct I {
   __event void f();   // C3748
};

int main() {
}
```