---
title: コンパイラ エラー C3530
ms.date: 11/04/2016
f1_keywords:
- C3530
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
ms.openlocfilehash: 023d7f0a5d509c4b301a9985da8ea7feb1f3d203
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228831"
---
# <a name="compiler-error-c3530"></a>コンパイラ エラー C3530

' auto ' を他の型指定子と組み合わせることはできません

型指定子は、キーワードと共に使用され **`auto`** ます。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. キーワードを使用する変数宣言では、型指定子を使用しないで **`auto`** ください。

## <a name="example"></a>例

次の例では、変数 `x` がキーワードと型の両方で宣言されているため、C3530 が生成 **`auto`** **`int`** されます。この例は **/zc: auto**でコンパイルされるためです。

```cpp
// C3530.cpp
// Compile with /Zc:auto
int main()
{
   auto int x;   // C3530
   return 0;
}
```

## <a name="see-also"></a>関連項目

[auto キーワード](../../cpp/auto-keyword.md)
