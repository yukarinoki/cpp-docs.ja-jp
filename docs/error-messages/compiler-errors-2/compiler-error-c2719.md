---
title: コンパイラ エラー C2719 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2719
dev_langs:
- C++
helpviewer_keywords:
- C2719
ms.assetid: ea6236d3-8286-45cc-9478-c84ad3dd3c8e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4423352bad520d66920a01542f592ed8022482d6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054188"
---
# <a name="compiler-error-c2719"></a>コンパイラ エラー C2719

'parameter': __declspec(align('#')) の仮引数はアラインされません。

[Align](../../cpp/align-cpp.md) `__declspec`修飾子は関数のパラメーターでは許可されていません。 関数パラメーターのアラインメントは、呼び出し規則によって制御されます。 詳細については、次を参照してください。[呼び出し規則](../../cpp/calling-conventions.md)します。

次の例は C2719 を生成し、その修正方法を示しています。

```
// C2719.cpp
void func(int __declspec(align(32)) i);   // C2719
// try the following line instead
// void func(int i);
```