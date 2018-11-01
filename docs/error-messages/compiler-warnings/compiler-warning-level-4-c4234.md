---
title: コンパイラの警告 (レベル 4) C4234
ms.date: 11/04/2016
f1_keywords:
- C4234
helpviewer_keywords:
- C4234
ms.assetid: f7fecd5c-8248-4fde-8446-502aedc357ca
ms.openlocfilehash: 314ee068fb2be6148304360b0aaa3bd8029c283b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441016"
---
# <a name="compiler-warning-level-4-c4234"></a>コンパイラの警告 (レベル 4) C4234

標準の拡張機能を使用します 'keyword' キーワードが予約済み。

コンパイラは、使用するキーワードをまだ実装していません。

この警告は、自動的にエラーになります。 この動作を変更する場合を使用して、 [#pragma warning](../../preprocessor/warning.md)します。 たとえば、レベル 4 の警告の問題、c4234

```
#pragma warning(2:4234)
```

をソース コード ファイルに追加します。