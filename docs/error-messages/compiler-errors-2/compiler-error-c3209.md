---
title: コンパイラ エラー C3209 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3209
dev_langs:
- C++
helpviewer_keywords:
- C3209
ms.assetid: 1de44e39-69d1-4894-8f89-ff92136e8e5d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d5df31170578c2462c3e437d6eb7f65d6b76af8b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048410"
---
# <a name="compiler-error-c3209"></a>コンパイラ エラー C3209

'class': ジェネリック クラスは、マネージ型または WinRTclass をする必要があります

ジェネリック クラスは、マネージド クラスまたは Windows ランタイム クラスである必要があります。

次の例では、C3209 を生成し、その修正方法を示しています。

```
// C3209.cpp
// compile with: /clr
generic <class T>
class C {};   // C3209

// OK - ref class can be generic
generic <class T>
ref class D {};
```