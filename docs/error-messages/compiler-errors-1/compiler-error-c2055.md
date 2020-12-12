---
description: 詳細については、「コンパイラエラー C2055」を参照してください。
title: コンパイラエラー C2055
ms.date: 11/04/2016
f1_keywords:
- C2055
helpviewer_keywords:
- C2055
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
ms.openlocfilehash: 0692488b8e1ea91fe235ade512c5fbe5094cdaef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174937"
---
# <a name="compiler-error-c2055"></a>コンパイラエラー C2055

型リストではなく、仮パラメーターリストが必要です

関数定義に、仮パラメーターリストではなくパラメーター型リストが含まれています。 ANSI C では、void または省略記号 () でない限り、仮パラメーターの名前を指定する必要があり `...` ます。

次の例では、C2055 が生成されます。

```c
// C2055.c
// compile with: /c
void func(int, char) {}  // C2055
void func (int i, char c) {}   // OK
```
