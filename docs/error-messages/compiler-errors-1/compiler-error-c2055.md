---
title: コンパイラ エラー C2055 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2055
dev_langs:
- C++
helpviewer_keywords:
- C2055
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6c63d79325417fbd9b1f451fb4a51f13957b4df
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019343"
---
# <a name="compiler-error-c2055"></a>コンパイラ エラー C2055

型リストではなく、仮パラメーター リストが必要です。

関数定義には、仮パラメーター リストではなく、パラメーターの型リストが含まれています。 ANSI C には、void または省略記号でない限り、名前を指定する正式なパラメーターが必要です。 (`...`)。

次の例では、C2055 が生成されます。

```
// C2055.c
// compile with: /c
void func(int, char) {}  // C2055
void func (int i, char c) {}   // OK
```