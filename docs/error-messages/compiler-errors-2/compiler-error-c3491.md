---
title: コンパイラ エラー C3491
ms.date: 11/04/2016
f1_keywords:
- C3491
helpviewer_keywords:
- C3491
ms.assetid: 7f0e71b2-46a0-4d25-bd09-6158a280f509
ms.openlocfilehash: 12f50e48fc18fc23d078b6dbc7d21d05efa06d43
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62381086"
---
# <a name="compiler-error-c3491"></a>コンパイラ エラー C3491

'var': 変更できないラムダでは値キャプチャは変更できません

変更できないラムダ式では、値によってキャプチャされる変数の値を変更できません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- `mutable` キーワードでラムダ式を宣言します。または、

- ラムダ式のキャプチャ リストへの参照によって変数を渡します。

## <a name="example"></a>例

次の例では、変更できないラムダ式の本体がキャプチャ変数 `m`を変更するため、C3491 が生成されます。

```
// C3491a.cpp

int main()
{
   int m = 55;
   [m](int n) { m = n; }(99); // C3491
}
```

## <a name="example"></a>例

次の例では、ラムダ式を `mutable` キーワードで宣言することで C3491 を解決しています。

```
// C3491b.cpp

int main()
{
   int m = 55;
   [m](int n) mutable { m = n; }(99);
}
```

## <a name="see-also"></a>関連項目

[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)