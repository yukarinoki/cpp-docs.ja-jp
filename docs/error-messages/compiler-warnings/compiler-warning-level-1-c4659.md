---
title: コンパイラの警告 (レベル 1) C4659
ms.date: 11/04/2016
f1_keywords:
- C4659
helpviewer_keywords:
- C4659
ms.assetid: e29ba8db-7917-43f6-8e34-868b752279ae
ms.openlocfilehash: 2aef25e922d8f38ac7103b1b12ccb31c282f0403
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374652"
---
# <a name="compiler-warning-level-1-c4659"></a>コンパイラの警告 (レベル 1) C4659

\#プラグマ ': #pragma comment (linker,...) を使用して、予約されたセグメント 'segment' の使用に未定義の動作を

オプションをリンカーに渡す .drectve オプションが使用されました。 代わりにプラグマを使用して、[コメント](../../preprocessor/comment-c-cpp.md)リンカー オプションを渡すためです。

```
// C4659.cpp
// compile with: /W1 /LD
#pragma code_seg(".drectve")   // C4659
```