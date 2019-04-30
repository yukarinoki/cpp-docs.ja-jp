---
title: コンパイラ エラー C3485
ms.date: 11/04/2016
f1_keywords:
- C3485
helpviewer_keywords:
- C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
ms.openlocfilehash: 2fcaecd6be35e2ae6822133930b48b6bbf02aafe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62381144"
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