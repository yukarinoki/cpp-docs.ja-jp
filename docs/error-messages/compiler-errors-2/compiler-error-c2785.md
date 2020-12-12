---
description: 詳細については、「コンパイラエラー C2785」を参照してください。
title: コンパイラエラー C2785
ms.date: 11/04/2016
f1_keywords:
- C2785
helpviewer_keywords:
- C2785
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
ms.openlocfilehash: f40b652e30b30f0ef17426b547337352181383e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297903"
---
# <a name="compiler-error-c2785"></a>コンパイラエラー C2785

' declaration1 ' と ' declaration2 ' の戻り値の型が異なります。

関数テンプレートの特殊化の戻り値の型が、プライマリ関数テンプレートの戻り値の型と異なります。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. 関数テンプレートのすべての特殊化を一貫性のために確認します。

## <a name="example"></a>例

次の例では、C2785 が生成されます。

```cpp
// C2785.cpp
// compile with: /c
template<class T> void f(T);

template<> int f(int); // C2785
template<> void f(int); // OK
```
