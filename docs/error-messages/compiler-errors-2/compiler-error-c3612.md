---
title: コンパイラ エラー C3612 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3612
dev_langs:
- C++
helpviewer_keywords:
- C3612
ms.assetid: aa6e3a2b-4afa-481c-98c1-1b6d1f82f869
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 16d960095942af34aa516341862c9a2bcf72bbba
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053688"
---
# <a name="compiler-error-c3612"></a>コンパイラ エラー C3612

'type': シール クラスを抽象にすることはできません

使用して定義されている型`value`は既定では、シール クラスは、その基本のすべてのメソッドを実装しない限り、抽象とします。 シールされた抽象クラスは基底クラスにもできます。 また、インスタンス化できます。

詳細については、次を参照してください。[クラスと構造体](../../windows/classes-and-structs-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では、C3612 が生成されます。

```
// C3612.cpp
// compile with: /clr /c
value struct V: public System::ICloneable {};   // C3612

// OK
value struct V2: public System::ICloneable {
   Object^ Clone();
};
```