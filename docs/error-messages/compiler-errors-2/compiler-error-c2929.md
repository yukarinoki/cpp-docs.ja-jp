---
title: コンパイラ エラー C2929 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2929
dev_langs:
- C++
helpviewer_keywords:
- C2929
ms.assetid: 11134027-6adc-4733-b6bd-b94486bd1933
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d7eee14296178fb90d4a3c34a28926032fcb04b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102828"
---
# <a name="compiler-error-c2929"></a>コンパイラ エラー C2929

'identifier': 明示的なインスタンス生成。明示的にテンプレート クラス メンバーのインスタンス生成を行ったり抑制したりできません

識別子がインスタンス化できないようになっている間は、識別子を明示的にインスタンス化することはできません。

次の例では C2929 が生成されます。

```
// C2929.cpp
// compile with: /c
template<typename T>
class A {
public:
   A() {}
};

template A<int>::A();

extern template A<int>::A();   // C2929
```