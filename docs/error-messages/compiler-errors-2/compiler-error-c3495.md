---
description: 詳細については、「コンパイラエラー C3495」を参照してください。
title: コンパイラ エラー C3495
ms.date: 11/04/2016
f1_keywords:
- C3495
helpviewer_keywords:
- C3495
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
ms.openlocfilehash: 3c04c80182dad32b539e09224fd9e303b3325578
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113169"
---
# <a name="compiler-error-c3495"></a>コンパイラ エラー C3495

'var': ラムダ キャプチャには自動ストレージ存続期間が指定されている必要があります

またはとマークされている変数など、自動ストレージ存続期間がない変数をキャプチャすることはできません **`static`** **`extern`** 。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- **`static`** または変数を、 **`extern`** ラムダ式のキャプチャリストに渡さないでください。

## <a name="example"></a>例

次の例では、 **`static`** `n` ラムダ式のキャプチャリストに変数があるため、C3495 が生成されます。

```cpp
// C3495.cpp

int main()
{
   static int n = 66;
   [&n]() { return n; }(); // C3495
}
```

## <a name="see-also"></a>関連項目

[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)
