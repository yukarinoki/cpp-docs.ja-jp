---
title: コンパイラ エラー C3199
ms.date: 11/04/2016
f1_keywords:
- C3199
helpviewer_keywords:
- C3199
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
ms.openlocfilehash: 934e980149ad893e6799b0ab119a148fc5652fdc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402789"
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