---
description: 詳細については、「コンパイラエラー C2957」を参照してください。
title: コンパイラ エラー C2957
ms.date: 11/04/2016
f1_keywords:
- C2957
helpviewer_keywords:
- C2957
ms.assetid: 9cb4526f-4af8-47e9-b786-56192627ca72
ms.openlocfilehash: 7d5539f43651feb930b3eb0f81677aaed0fa6b4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210583"
---
# <a name="compiler-error-c2957"></a>コンパイラ エラー C2957

'delim': 無効な左側の区切り文字です: '<' が必要です

ジェネリック クラスの形式が正しくありません。

次の例では C2957 が生成されます。

```cpp
// C2957.cpp
// compile with: /clr /LD
generic << class T>   // C2957
// try the following line instead
// generic < class T>
gc class C {};
```
