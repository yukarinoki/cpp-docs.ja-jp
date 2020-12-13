---
description: 詳細については、「コンパイラエラー C2754」を参照してください。
title: コンパイラエラー C2754
ms.date: 11/04/2016
f1_keywords:
- C2754
helpviewer_keywords:
- C2754
ms.assetid: 1cab66c5-da9d-4b81-b7fb-9cdc48ff1ccc
ms.openlocfilehash: 68840f85d7a7f9be18246dfa4f3176a76f0fb9ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336219"
---
# <a name="compiler-error-c2754"></a>コンパイラエラー C2754

' 特殊化 ': 部分的特殊化は、依存しない非型テンプレートパラメーターを持つことはできません

依存しない非型テンプレートパラメーターを持つテンプレートクラスを部分的に特殊化しようとしました。 これは認められていません。

次の例では、C2754 が生成されます。

```cpp
// C2754.cpp
// compile with: /c

template<class T, T t>
struct A {};

template<class T, int N>
struct B {};

template<class T> struct A<T,5> {};   // C2754
template<> struct A<int,5> {};   // OK
template<class T> struct B<T,5> {};   // OK
```
