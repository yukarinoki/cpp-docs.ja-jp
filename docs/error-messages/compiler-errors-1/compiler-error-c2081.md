---
title: コンパイラ エラー C2081 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2081
dev_langs:
- C++
helpviewer_keywords:
- C2081
ms.assetid: 7db9892d-364d-4178-a49d-f8398ece09a0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 48f2cdecaea38beed14735bb3f94c8422a28c747
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030457"
---
# <a name="compiler-error-c2081"></a>コンパイラ エラー C2081

'identifier': 仮パラメーター リストが不正です名。

識別子には、構文エラーが発生しました。

このエラーは、仮パラメーター リストの古いスタイルを使用して発生することができます。 仮パラメーター リストでは、仮パラメーターの種類を指定する必要があります。

次の例では、C2081 が生成されます。

```
// C2081.c
void func( int i, j ) {}  // C2081, no type specified for j
```

考えられる解決方法:

```
// C2081b.c
// compile with: /c
void func( int i, int j ) {}
```