---
title: コンパイラ エラー C3199 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3199
dev_langs:
- C++
helpviewer_keywords:
- C3199
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ed917b3711f7f757b0a4ad89f0e6594ea1642a9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027280"
---
# <a name="compiler-error-c3199"></a>コンパイラ エラー C3199

無効な浮動小数点プラグマの使用: 例外は precise でないモードでサポートされていません

[Float_control](../../preprocessor/float-control.md)プラグマを使用した 浮動小数点例外モデルを指定する、 [/fp](../../build/reference/fp-specify-floating-point-behavior.md)以外に設定 **/fp: 正確な**します。

次の例では、C3199 が生成されます。

```
// C3199.cpp
// compile with: /fp:fast
#pragma float_control(except, on)   // C3199
```