---
title: コンパイラ エラー C3139
ms.date: 11/04/2016
f1_keywords:
- C3139
helpviewer_keywords:
- C3139
ms.assetid: 95c92263-10ac-4ff3-b385-6312dd92adbc
ms.openlocfilehash: f224be74a94e0e769e7c26bc99b4790d69f6b65b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50521204"
---
# <a name="compiler-error-c3139"></a>コンパイラ エラー C3139

'struct': メンバーなしに UDT をエクスポートすることはできません

適用しようとして、[エクスポート](../../windows/export.md)属性を空の UDT (ユーザー定義型)。 例えば:

```
// C3139.cpp
#include "unknwn.h"
[emitidl];
[module(name=xx)];

[export] struct MyStruct {   // C3139 empty type
};
int main(){}
```