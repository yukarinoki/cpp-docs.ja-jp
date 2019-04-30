---
title: コンパイラ エラー C3354
ms.date: 11/04/2016
f1_keywords:
- C3354
helpviewer_keywords:
- C3354
ms.assetid: 185de401-231e-4999-a149-172ee4c69d84
ms.openlocfilehash: 1ff2967f602722c99b58b679324bd4f50575f109
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402607"
---
# <a name="compiler-error-c3354"></a>コンパイラ エラー C3354

'function': デリゲートを作成するための関数に、戻り値の型 'type' を指定することはできません。

次の型は、 `delegate`の戻り値の型として正しくありません。

- 関数へのポインター

- メンバーへのポインター

- メンバー関数へのポインター

- 関数への参照

- メンバー関数への参照

次の例では C3354 が生成されます。

```
// C3354_2.cpp
// compile with: /clr /c
using namespace System;
typedef void ( *VoidPfn )();

delegate VoidPfn func(); // C3354
// try the following line instead
// delegate  void func();
```
