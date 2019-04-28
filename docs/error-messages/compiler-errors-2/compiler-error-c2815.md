---
title: コンパイラ エラー C2815
ms.date: 11/04/2016
f1_keywords:
- C2815
helpviewer_keywords:
- C2815
ms.assetid: d0256fd6-0721-4c99-b03c-52d96e77a613
ms.openlocfilehash: ab6708e7ae0a56bd71adebad4fb42d6ea9abe116
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175408"
---
# <a name="compiler-error-c2815"></a>コンパイラ エラー C2815

'operator delete': 最初の仮パラメーターがある必要があります ' void *'、'param' の使用

ユーザー定義[delete 演算子](../../standard-library/new-operators.md#op_delete)関数は、型の最初の仮パラメーターを受け取る必要があります`void *`します。

次の例では、C2815 が生成されます。

```
// C2815.cpp
// compile with: /c
class CMyClass {
public:
   void mf1(int *a);
   void operator delete(CMyClass *);   // C2815
   void operator delete(void *);
};
```