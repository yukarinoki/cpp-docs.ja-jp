---
title: コンパイラ エラー C2824 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2824
dev_langs:
- C++
helpviewer_keywords:
- C2824
ms.assetid: 5bd865f7-e0af-404e-80fe-e2b798b44a59
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 310156e82f69622a5c4a2315e204ccaa146e2c00
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077413"
---
# <a name="compiler-error-c2824"></a>コンパイラ エラー C2824

型の戻り値の 'operator new' である必要があります ' void *'

演算子のオーバー ロードとベース以外のポインター、`new`返す必要があります`void *`します。

次の例では、C2824 が生成されます。

```
// C2824.cpp
// compile with: /c
class   A {
   A* operator new(size_t i, char *m);   // C2824
   // try the following line instead
   // void* operator new(size_t i, char *m);
};
```