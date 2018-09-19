---
title: コンパイラ エラー C3174 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3174
dev_langs:
- C++
helpviewer_keywords:
- C3174
ms.assetid: fe6b3b5a-8196-485f-a45f-0b2e51df4086
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1ca73c1fa16f2cc8b25f355705c7f0a72916158d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46105189"
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