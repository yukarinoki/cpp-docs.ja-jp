---
title: コンパイラ エラー C3491
ms.date: 11/04/2016
f1_keywords:
- C3491
helpviewer_keywords:
- C3491
ms.assetid: 7f0e71b2-46a0-4d25-bd09-6158a280f509
ms.openlocfilehash: f6f20d9af424fdd4254fc15e0580d62b9dfba144
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87184476"
---
# <a name="compiler-error-c3491"></a>コンパイラ エラー C3491

'var': 変更できないラムダでは値キャプチャは変更できません

変更できないラムダ式では、値によってキャプチャされる変数の値を変更できません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- キーワードを使用してラムダ式を宣言します。 **`mutable`**

- ラムダ式のキャプチャ リストへの参照によって変数を渡します。

## <a name="example"></a>例

次の例では、変更できないラムダ式の本体がキャプチャ変数 `m`を変更するため、C3491 が生成されます。

```cpp
// C3491a.cpp

int main()
{
   int m = 55;
   [m](int n) { m = n; }(99); // C3491
}
```

## <a name="example"></a>例

次の例では、ラムダ式をキーワードで宣言することによって、C3491 を解決し **`mutable`** ます。

```cpp
// C3491b.cpp

int main()
{
   int m = 55;
   [m](int n) mutable { m = n; }(99);
}
```

## <a name="see-also"></a>関連項目

[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)
