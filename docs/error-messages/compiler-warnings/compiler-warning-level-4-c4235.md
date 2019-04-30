---
title: コンパイラの警告 (レベル 4) C4235
ms.date: 11/04/2016
f1_keywords:
- C4235
helpviewer_keywords:
- C4235
ms.assetid: d4214799-d62c-4674-b4e2-9e201c303303
ms.openlocfilehash: 80ad388b26b2b972aa1301c1f335d0361a75f15f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401047"
---
# <a name="compiler-warning-level-4-c4235"></a>コンパイラの警告 (レベル 4) C4235

非標準の拡張機能が使用されています : 'キーワード' キーワードはこのアーキテクチャではサポートされていません

使用したキーワードは、サポートされていません。

この警告は、自動的にエラーになります。 この動作を変更する場合を使用して、 [#pragma warning](../../preprocessor/warning.md)します。 たとえば、C4235 でレベル 2 の警告を発行させるには、

```
#pragma warning(2:4235)
```

をソース コード ファイルに追加します。