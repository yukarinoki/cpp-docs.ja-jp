---
title: コンパイラの警告 (レベル 1) C4659
ms.date: 11/04/2016
f1_keywords:
- C4659
helpviewer_keywords:
- C4659
ms.assetid: e29ba8db-7917-43f6-8e34-868b752279ae
ms.openlocfilehash: 1766cb285fa33d384d57e89c7243fc35022ae006
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175637"
---
# <a name="compiler-warning-level-1-c4659"></a>コンパイラの警告 (レベル 1) C4659

\#プラグマ ' pragma ': 予約セグメント ' segment ' の使用には定義されていない動作があります。 #pragma コメントを使用してください (リンカー,...)

.Drectve オプションは、リンカーにオプションを渡すために使用されました。 代わりに、リンカーオプションを渡すためにプラグマ[コメント](../../preprocessor/comment-c-cpp.md)を使用してください。

```cpp
// C4659.cpp
// compile with: /W1 /LD
#pragma code_seg(".drectve")   // C4659
```
