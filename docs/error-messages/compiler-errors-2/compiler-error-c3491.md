---
title: コンパイラ エラー C3491
ms.date: 11/04/2016
f1_keywords:
- C3491
helpviewer_keywords:
- C3491
ms.assetid: 7f0e71b2-46a0-4d25-bd09-6158a280f509
ms.openlocfilehash: 8e59dd44b81846d48dc5bf7172ce17444f75e6ef
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2020
ms.locfileid: "90685711"
---
# <a name="compiler-error-c3491"></a>コンパイラ エラー C3491

'var': 変更できないラムダでは値キャプチャは変更できません

変更できないラムダ式では、値によってキャプチャされる変数の値を変更できません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- キーワードを使用してラムダ式を宣言します。 **`mutable`**

- ラムダ式のキャプチャ リストへの参照によって変数を渡します。

## <a name="examples"></a>例

次の例では、変更できないラムダ式の本体がキャプチャ変数 `m`を変更するため、C3491 が生成されます。

```cpp
// C3491a.cpp

int main()
{
   int m = 55;
   [m](int n) { m = n; }(99); // C3491
}
```

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
