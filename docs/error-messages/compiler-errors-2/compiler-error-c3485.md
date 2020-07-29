---
title: コンパイラ エラー C3485
ms.date: 11/04/2016
f1_keywords:
- C3485
helpviewer_keywords:
- C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
ms.openlocfilehash: 2117832ffd5a90612e9745a3706f01e3b5d1b18d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87197671"
---
# <a name="compiler-error-c3485"></a>コンパイラ エラー C3485

ラムダ定義に cv 修飾子は使用できません

**`const`** **`volatile`** ラムダ式の定義の一部としてまたは修飾子を使用することはできません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- **`const`** **`volatile`** ラムダ式の定義から修飾子または修飾子を削除します。

## <a name="example"></a>例

次の例では、 **`const`** ラムダ式の定義の一部として修飾子を使用するため、C3485 が生成されます。

```cpp
// C3485.cpp

int main()
{
   auto x = []() const mutable {}; // C3485
}
```

## <a name="see-also"></a>関連項目

[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)
