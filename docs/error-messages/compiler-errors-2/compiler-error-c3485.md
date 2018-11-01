---
title: コンパイラ エラー C3485
ms.date: 11/04/2016
f1_keywords:
- C3485
helpviewer_keywords:
- C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
ms.openlocfilehash: 09080a402767835cda9711c2f0fc4d7c8d787439
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508022"
---
# <a name="compiler-error-c3485"></a>コンパイラ エラー C3485

ラムダ定義に cv 修飾子は使用できません

ラムダ式の定義の一部として `const` 修飾子または `volatile` 修飾子を使用することはできません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- ラムダ式の定義から `const` 修飾子または `volatile` 修飾子を削除します。

## <a name="example"></a>例

次の例では、ラムダ式の定義の一部として `const` 修飾子を使用しているため、C3485 が生成されます。

```
// C3485.cpp

int main()
{
   auto x = []() const mutable {}; // C3485
}
```

## <a name="see-also"></a>関連項目

[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)