---
description: 詳細については、「コンパイラエラー C2731」を参照してください。
title: コンパイラエラー C2731
ms.date: 11/04/2016
f1_keywords:
- C2731
helpviewer_keywords:
- C2731
ms.assetid: 9b563999-febd-4582-9147-f355083c091e
ms.openlocfilehash: baae65ff1d09bafe37251b7593dc0d0c91c89f1b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123306"
---
# <a name="compiler-error-c2731"></a>コンパイラエラー C2731

' identifier ': 関数をオーバーロードすることはできません

関数、 `main` 、 `WinMain` `DllMain` 、およびは `LibMain` オーバーロードできません。

次の例では、C2731 が生成されます。

```cpp
// C2731.cpp
extern "C" void WinMain(int, char *, char *);
void WinMain(int, short, char *, char*);   // C2731
```
