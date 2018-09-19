---
title: コンパイラ エラー C2652 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2652
dev_langs:
- C++
helpviewer_keywords:
- C2652
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 37b7b259b8eb42692641883c8d69578542cce06e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076620"
---
# <a name="compiler-error-c2652"></a>コンパイラ エラー C2652

'identifier': コピー コンス トラクター: 最初のパラメーターが 'identifier' を認めない

コピー コンス トラクターの最初のパラメーターは、クラス、構造体または共用体が定義されているのと同じ型です。 最初のパラメーターは、型が型自体への参照を指定できます。

次の例では、C2651 が生成されます。

```
// C2652.cpp
// compile with: /c
class A {
   A( A );   // C2652 takes an A
};
class B {
   B( B& );   // OK, reference to B
};
```