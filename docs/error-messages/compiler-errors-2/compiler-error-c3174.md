---
title: コンパイラ エラー C3174
ms.date: 11/04/2016
f1_keywords:
- C3174
helpviewer_keywords:
- C3174
ms.assetid: fe6b3b5a-8196-485f-a45f-0b2e51df4086
ms.openlocfilehash: 32f39eb1d808ccedd27ae3e4d343b87ddfde1862
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174121"
---
# <a name="compiler-error-c3174"></a>コンパイラ エラー C3174

モジュール属性は指定されませんでした。

Visual C 属性を使用するプログラムは使用しなかったも、[モジュール](../../windows/module-cpp.md)属性には、属性を使用する任意のプログラムが必要です。

次の例では、C3174 が生成されます。

```
// C3174.cpp
// C3174 expected
// uncomment the following line to resolve this C3174
// [module(name="x")];
[export]
struct S
{
   int i;
};

int main()
{
}
```