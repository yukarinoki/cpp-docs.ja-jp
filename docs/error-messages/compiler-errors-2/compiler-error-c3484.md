---
title: コンパイラ エラー C3484
ms.date: 11/04/2016
f1_keywords:
- C3484
helpviewer_keywords:
- C3484
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
ms.openlocfilehash: c4405eb81911b1081d19d25ba779d24bee8f6d37
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039979"
---
# <a name="compiler-error-c3484"></a>コンパイラ エラー C3484

戻り値の型の前に '->' が必要です

ラムダ式の戻り値の型の前に `->` を指定する必要があります。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- 戻り値の型の前に `->` を指定します。

## <a name="example"></a>例

次の例では C3484 が生成されます。

```
// C3484a.cpp

int main()
{
   return []() . int { return 42; }(); // C3484
}
```

## <a name="example"></a>例

次の例では、ラムダ式の戻り値の型の前に `->` を指定して C3484 を解決します。

```
// C3484b.cpp

int main()
{
   return []() -> int { return 42; }();
}
```

## <a name="see-also"></a>関連項目

[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)