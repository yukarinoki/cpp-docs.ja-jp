---
description: 詳細については、「コンパイラエラー C3484」を参照してください。
title: コンパイラ エラー C3484
ms.date: 11/04/2016
f1_keywords:
- C3484
helpviewer_keywords:
- C3484
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
ms.openlocfilehash: 6d3e72ef89ad33333c840b549cfc5c7c40495130
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315687"
---
# <a name="compiler-error-c3484"></a>コンパイラ エラー C3484

戻り値の型の前に '->' が必要です

ラムダ式の戻り値の型の前に `->` を指定する必要があります。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- 戻り値の型の前に `->` を指定します。

## <a name="examples"></a>例

次の例では C3484 が生成されます。

```cpp
// C3484a.cpp

int main()
{
   return []() . int { return 42; }(); // C3484
}
```

次の例では、ラムダ式の戻り値の型の前に `->` を指定して C3484 を解決します。

```cpp
// C3484b.cpp

int main()
{
   return []() -> int { return 42; }();
}
```

## <a name="see-also"></a>関連項目

[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)
