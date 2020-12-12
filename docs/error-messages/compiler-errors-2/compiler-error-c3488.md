---
description: 詳細については、「コンパイラエラー C3488」を参照してください。
title: コンパイラ エラー C3488
ms.date: 11/04/2016
f1_keywords:
- C3488
helpviewer_keywords:
- C3488
ms.assetid: 0a6fcd76-dd3b-48d7-abb3-22eccda96034
ms.openlocfilehash: a18578543e452a58e392bcfc9927777e6546011d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113381"
---
# <a name="compiler-error-c3488"></a>コンパイラ エラー C3488

既定のキャプチャ モードが参照キャプチャである場合、'var' は使用できません

ラムダ式の既定のキャプチャ モードが参照渡しであるを指定する場合は、その式の capture 句に参照によって変数を渡すことができません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- capture 句に明示的に変数を渡さないでください。

- 既定のキャプチャ モードとして参照渡しを指定しないでください。

- 既定のキャプチャ モードとして値渡しを指定します。

- capture 句に値によって変数を渡します。 (これにより、ラムダ式の動作が変更される可能性があります。)

## <a name="examples"></a>例

次の例では、変数 `n` への参照が、既定モードが参照渡しであるラムダ式の capture 句にあるため、C3488 が生成されます。

```cpp
// C3488a.cpp

int main()
{
   int n = 5;
   [&, &n]() { return n; } (); // C3488
}
```

次の例では、C3488 について考えられる 4 つの解決策を示します。

```cpp
// C3488b.cpp

int main()
{
   int n = 5;

   // Possible resolution 1:
   // Do not explicitly pass &n to the capture clause.
   [&]() { return n; } ();

   // Possible resolution 2:
   // Do not specify by-reference as the default capture mode.
   [&n]() { return n; } ();

   // Possible resolution 3:
   // Specify by-value as the default capture mode.
   [=, &n]() { return n; } ();

   // Possible resolution 4:
   // Pass n by value to the capture clause.
   [n]() { return n; } ();
}
```

## <a name="see-also"></a>関連項目

[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)
