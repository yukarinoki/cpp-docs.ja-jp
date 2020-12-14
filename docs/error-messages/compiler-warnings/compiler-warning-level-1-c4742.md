---
description: '詳細情報: コンパイラの警告 (レベル 1) C4742'
title: コンパイラの警告 (レベル 1) C4742
ms.date: 07/22/2020
f1_keywords:
- C4742
helpviewer_keywords:
- C4742
ms.assetid: e520881d-1eeb-48b1-9df0-8017ee8ba076
ms.openlocfilehash: 009c8b894b9c53d3a0c802dbb0f5786fc9934b57
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228522"
---
# <a name="compiler-warning-level-1-c4742"></a>コンパイラの警告 (レベル 1) C4742

> '*変数*' は、'*file1*' と '*file2*' で異なるアラインメントを含んでいます: *number1* と *number2*

2つのファイルで参照または定義された外部変数は、それらのファイル内で異なるアラインメントを持ちます。

## <a name="remarks"></a>解説

この警告は、コンパイラが file1 の変数に対して、file2 の変数に対してと異なることを検出した場合に生成され **`alignof`**  **`alignof`** ます。  異なるファイルで変数を宣言する場合、または異なるファイルで一致しない場合に、互換性のない型を使用することによって、この問題が発生することがあり `#pragma pack` ます。

この警告を解決するには、同じ型定義を使用するか、変数に別の名前を使用します。

詳細については、「」および「演算子」を参照してください [`pack`](../../preprocessor/pack.md) 。 [ `alignof` ](../../cpp/alignof-operator.md)

## <a name="example"></a>例

これは、型を定義する最初のファイルです。

```c
// C4742a.c
// compile with: /c
struct X {
   char x, y, z, w;
} global;
```

次の例では、C4742 が生成されます。

```c
// C4742b.c
// compile with: C4742a.c /W1 /GL
// C4742 expected
extern struct X {
   int a;
} global;

int main() {
   global.a = 0;
}
```
