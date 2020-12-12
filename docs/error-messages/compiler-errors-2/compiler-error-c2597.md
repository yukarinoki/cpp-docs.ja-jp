---
description: 詳細については、「コンパイラエラー C2597」を参照してください。
title: コンパイラ エラー C2597
ms.date: 11/04/2016
f1_keywords:
- C2597
helpviewer_keywords:
- C2597
ms.assetid: 2e48127d-e3ff-4a40-8156-2863e45b1a38
ms.openlocfilehash: b3430da85cef961b7c26b55e8dee9f1911533faf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120140"
---
# <a name="compiler-error-c2597"></a>コンパイラ エラー C2597

静的でないメンバー 'identifier' への参照が正しくありません。

次の原因が考えられます。

1. 静的でないメンバーが静的メンバー関数に指定されている。 静的でないメンバーにアクセスするには、クラスのローカル インスタンスを渡すかまたは作成し、メンバー アクセス演算子 (`.` または `->`) を使用する必要があります。

1. 指定された識別子が、クラス、構造体、または共用体のメンバーではない。 識別子のスペルを確認します。

1. メンバー アクセス演算子が非メンバー関数を参照している。

1. 次の例では、C2597 を生成し、その修正方法を示しています。

```cpp
// C2597.cpp
// compile with: /c
struct s1 {
   static void func();
   static void func2(s1&);
   int i;
};

void s1::func() {
   i = 1;    // C2597 - static function can't access non-static data member
}

// OK - fix by passing an instance of s1
void s1::func2(s1& a) {
   a.i = 1;
}
```
