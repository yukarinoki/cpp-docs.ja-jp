---
title: コンパイラの警告 (レベル 4) C4212
ms.date: 11/04/2016
f1_keywords:
- C4212
helpviewer_keywords:
- C4212
ms.assetid: df781ea1-182d-4f9f-9a31-55b6ce80c711
ms.openlocfilehash: d33e5c60bac657060ffef2a43686a5f737eb11cc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161309"
---
# <a name="compiler-warning-level-4-c4212"></a>コンパイラの警告 (レベル 4) C4212

非標準の拡張機能が使用されています: 省略記号を使用する関数宣言

関数プロトタイプには、可変個の引数があります。 関数定義ではありません。

次の例では、C4212 が生成されます。

```c
// C4212.c
// compile with: /W4 /Ze /c
void f(int , ...);
void f(int i, int j) {}
```
