---
title: コンパイラ エラー C2998 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2998
dev_langs:
- C++
helpviewer_keywords:
- C2998
ms.assetid: 8193d491-b5d9-4477-acb1-cf166889c070
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 181db50f9b2598379d1b9d56720551f1b18cbf18
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118428"
---
# <a name="compiler-error-c2998"></a>コンパイラ エラー C2998

'identifier': テンプレート定義ではありません

コンパイラはテンプレート定義で使用されている構文を処理できませんでした。

次の例では C2998 が生成されます。

```
// C2998.cpp
// compile with: /c
template <class T> int x = 1018; // C2998
```