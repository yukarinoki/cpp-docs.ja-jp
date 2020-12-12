---
description: 詳細については、「コンパイラエラー C3768」を参照してください。
title: コンパイラ エラー C3768
ms.date: 11/04/2016
f1_keywords:
- C3768
helpviewer_keywords:
- C3768
ms.assetid: 091f0d53-1dff-43fd-813d-5c43c85b6ab0
ms.openlocfilehash: 3203fe74fb1da91f24312f76ca11ac49711da8f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291715"
---
# <a name="compiler-error-c3768"></a>コンパイラ エラー C3768

> 純粋マネージコードで仮想 vararg 関数のアドレスを取得することはできません

## <a name="remarks"></a>解説

**/Clr: pure** コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

**/Clr: pure** を使用してコンパイルする場合、仮想関数のアドレスを取得することはできません `vararg` 。

## <a name="example"></a>例

次の例では、C3768 が生成されます。

```cpp
// C3768.cpp
// compile with: /clr:pure
struct A
{
   virtual void f(...);
};

int main()
{
   &(A::f);   // C3768
}
```
