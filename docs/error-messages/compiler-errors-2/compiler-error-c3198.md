---
description: 詳細については、「コンパイラエラー C3198」を参照してください。
title: コンパイラエラー C3198
ms.date: 11/04/2016
f1_keywords:
- C3198
helpviewer_keywords:
- C3198
ms.assetid: ec4ecf61-0067-4aa4-b443-a91013a1e59d
ms.openlocfilehash: 8f72dd32af7f004696afd87b7141768f09ea5f12
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321984"
---
# <a name="compiler-error-c3198"></a>コンパイラエラー C3198

浮動小数点プラグマの使い方が正しくありません: fenv_access プラグマは正確なモードでのみ動作します

[fenv_access](../../preprocessor/fenv-access.md)プラグマが **/fp: 精密** 以外の [/fp](../../build/reference/fp-specify-floating-point-behavior.md)設定で使用されました。

次の例では、C3198 が生成されます。

```cpp
// C3198.cpp
// compile with: /fp:fast
#pragma fenv_access(on)   // C3198
```
