---
description: 詳細については、「コンパイラエラー C2755」を参照してください。
title: コンパイラエラー C2755
ms.date: 11/04/2016
f1_keywords:
- C2755
helpviewer_keywords:
- C2755
ms.assetid: 8ee4eeb6-4757-4efe-9100-38ff4a96f1de
ms.openlocfilehash: dcf597505afb170aaf87644a7482a56dc2fdc73c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336215"
---
# <a name="compiler-error-c2755"></a>コンパイラエラー C2755

' param ': 部分的特殊化の非型パラメーターは、単純な識別子でなければなりません

非型パラメーターは、単純な識別子である必要があります。これは、コンパイル時にコンパイラが単一の識別子または定数値に解決できるものです。

次の例では、C2755 が生成されます。

```cpp
// C2755.cpp
template<int I, int J>
struct A {};

template<int I>
struct A<I,I*5> {};   // C2755
// try the following line instead
// struct A<I,5> {};
```
