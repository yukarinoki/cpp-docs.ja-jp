---
description: 詳細については、「コンパイラエラー C2612」を参照してください。
title: コンパイラエラー C2612
ms.date: 11/04/2016
f1_keywords:
- C2612
helpviewer_keywords:
- C2612
ms.assetid: 6faacfd6-4455-41a2-808e-0f6799f84d6d
ms.openlocfilehash: 34ff229f493ccbab8c41e011caaabea818d79de9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338682"
---
# <a name="compiler-error-c2612"></a>コンパイラエラー C2612

基底クラスまたはメンバー初期化子リストの末尾にある ' char ' は無効です

初期化子リストの最後のベースまたはメンバーの後に文字が表示されます。

次の例では、C2612 が生成されます。

```cpp
// C2612.cpp
class A {
public:
   int i;
   A( int ia ) : i( ia ) + {};   // C2612
};
```
