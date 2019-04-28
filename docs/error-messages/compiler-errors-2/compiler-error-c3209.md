---
title: コンパイラ エラー C3209
ms.date: 11/04/2016
f1_keywords:
- C3209
helpviewer_keywords:
- C3209
ms.assetid: 1de44e39-69d1-4894-8f89-ff92136e8e5d
ms.openlocfilehash: f907d0605cccf0a36abd1361d8c87a783bb81506
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243246"
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