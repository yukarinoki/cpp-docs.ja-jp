---
title: コンパイラ エラー C2243
ms.date: 11/04/2016
f1_keywords:
- C2243
helpviewer_keywords:
- C2243
ms.assetid: b90065bb-d251-4ba9-8b4c-280ee13fa9c0
ms.openlocfilehash: ab0dbe8c5595c18a01f78c22056803dce91a3f31
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212840"
---
# <a name="compiler-error-c2243"></a>コンパイラ エラー C2243

'type1' から 'type2' の 'conversion type' 変換は存在しますが、アクセスできません。

アクセス保護 ( **`protected`** または) では、 **`private`** 派生クラスへのポインターから基底クラスへのポインターへの変換ができませんでした。

次の例では C2243 が生成されます。

```cpp
// C2243.cpp
// compile with: /c
class B {};
class D : private B {};
class E : public B {};

D d;
B *p = &d;   // C2243

E e;
B *p2 = &e;
```

またはへのアクセスがある基本クラス **`protected`** **`private`** には、派生クラスのクライアントからアクセスできません。 これらのレベルのアクセス制御は、基底クラスが、クライアントに表示される必要がない実装の詳細であることを示すために使用されます。 派生クラスのクライアントが派生クラスのポインターから基底クラスへのポインターへの暗黙的な変換にアクセスする必要がある場合は、パブリック派生を使用します。
