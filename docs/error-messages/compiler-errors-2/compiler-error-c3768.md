---
title: コンパイラ エラー C3768
ms.date: 11/04/2016
f1_keywords:
- C3768
helpviewer_keywords:
- C3768
ms.assetid: 091f0d53-1dff-43fd-813d-5c43c85b6ab0
ms.openlocfilehash: 534be9e3873276313335ca921264be92c9259b93
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165744"
---
# <a name="compiler-error-c3768"></a>コンパイラ エラー C3768

> 純粋マネージコードで仮想 vararg 関数のアドレスを取得することはできません

## <a name="remarks"></a>解説

**/Clr: pure**コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

**/Clr: pure**を使用してコンパイルする場合、仮想 `vararg` 関数のアドレスを取得することはできません。

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
