---
title: コンパイラ エラー C3485
ms.date: 11/04/2016
f1_keywords:
- C3485
helpviewer_keywords:
- C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
ms.openlocfilehash: 2fcaecd6be35e2ae6822133930b48b6bbf02aafe
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59027585"
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