---
description: 詳細については、「コンパイラエラー C3485」を参照してください。
title: コンパイラ エラー C3485
ms.date: 11/04/2016
f1_keywords:
- C3485
helpviewer_keywords:
- C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
ms.openlocfilehash: 0b11eb4487a9b6deb611852dd11a8a1963dd961e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168385"
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
