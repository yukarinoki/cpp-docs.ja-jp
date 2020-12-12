---
description: 詳細については、「コンパイラエラー C2380」を参照してください。
title: コンパイラ エラー C2380
ms.date: 11/04/2016
f1_keywords:
- C2380
helpviewer_keywords:
- C2380
ms.assetid: 717b1e6e-ddfe-4bac-a5f3-7f9a4dcb1572
ms.openlocfilehash: 4455fef072b6d8f686d5f43130db8d02aba69fd1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174690"
---
# <a name="compiler-error-c2380"></a>コンパイラ エラー C2380

' identifier ' の前の型 (戻り値の型を持つコンストラクター、または現在のクラス名の再定義が無効です)

コンストラクターは、値を返すか、またはクラス名を再定義します。

次の例では C2326 が生成されます。

```cpp
// C2380.cpp
// compile with: /c
class C {
public:
   int C();   // C2380, specifies an int return
   int C;   // C2380, redefinition of i
   C();   // OK
};
```
