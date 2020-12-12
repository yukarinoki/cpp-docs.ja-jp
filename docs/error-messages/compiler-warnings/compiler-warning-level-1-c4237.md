---
description: '詳細情報: コンパイラの警告 (レベル 1) C4237'
title: コンパイラの警告 (レベル 1) C4237
ms.date: 11/04/2016
f1_keywords:
- C4237
helpviewer_keywords:
- C4237
ms.assetid: f2e86c4b-80d8-460e-9429-83c5f3f5d7ca
ms.openlocfilehash: a83c40d54a5bd711fbc399ac4880a211f3cf9bd7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266248"
---
# <a name="compiler-warning-level-1-c4237"></a>コンパイラの警告 (レベル 1) C4237

' keyword ' キーワードはまだサポートされていませんが、将来使用するために予約されています

C++ 仕様のキーワードは Microsoft C++ コンパイラでは実装されていませんが、キーワードはユーザー定義シンボルとして使用できません。

次の例では、C4237 が生成されます。

```cpp
// C4237.cpp
// compile with: /W1 /c
int export;   // C4237
```
