---
description: 詳細については、「コンパイラエラー C3493」を参照してください。
title: コンパイラ エラー C3493
ms.date: 11/04/2016
f1_keywords:
- C3493
helpviewer_keywords:
- C3493
ms.assetid: 734b4257-12a3-436f-8488-c8c55ec81634
ms.openlocfilehash: 8f16a53dbaf5b9924a4874d29d560f9c089eb244
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315531"
---
# <a name="compiler-error-c3493"></a>コンパイラ エラー C3493

既定のキャプチャ モードが指定されていないため、'var' を暗黙的にキャプチャできません

空のラムダ式のキャプチャである `[]`は、ラムダ式が明示的にも暗黙的にも変数をキャプチャしないことを指定します。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- 既定のキャプチャ モードを指定するか、または

- 1 つ以上の変数を明示的にキャプチャします。

## <a name="examples"></a>例

次の例では、外部変数を変更しているが、空のキャプチャ句を指定していないため、C3493 が生成されます。

```cpp
// C3493a.cpp

int main()
{
   int m = 55;
   [](int n) { m = n; }(99); // C3493
}
```

次の例では、既定のキャプチャ モードとして参照渡しを指定することによって C3493 を解決しています。

```cpp
// C3493b.cpp

int main()
{
   int m = 55;
   [&](int n) { m = n; }(99);
}
```

## <a name="see-also"></a>関連項目

[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)
