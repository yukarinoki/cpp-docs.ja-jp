---
title: コンパイラエラー C2703
description: Microsoft C/c + + コンパイラエラー C2703 について説明します。
ms.date: 08/24/2020
f1_keywords:
- C2703
helpviewer_keywords:
- C2703
ms.assetid: 384295c3-643d-47ae-a9a6-865b3036aa84
ms.openlocfilehash: 4d5b5ccad1cd15c1a107c81423e2372e14165776
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898605"
---
# <a name="compiler-error-c2703"></a>コンパイラエラー C2703

> 無効な `__leave` ステートメント

## <a name="remarks"></a>注釈

ステートメントは、 **`__leave`** ブロック内になければなりません **`__try`** 。

## <a name="example"></a>例

次の例では、C2703 が生成されます。

```cpp
// C2703.cpp
int main() {
   __leave;   // C2703
   __try {
      // try the following line instead
      __leave;
   }
   __finally {}
}
```

## <a name="see-also"></a>関連項目

[`__leave`キーワード](../../cpp/try-except-statement.md#__leave)\
[`try-except` 諸表](../../cpp/try-except-statement.md)\
[`try-finally` ステートメント](../../cpp/try-finally-statement.md)
