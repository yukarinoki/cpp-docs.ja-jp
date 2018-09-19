---
title: コンパイラ エラー C2516 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2516
dev_langs:
- C++
helpviewer_keywords:
- C2516
ms.assetid: cd3accc1-0179-4a13-9587-616908c4ad1d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 56262d7f3b3e1b21c4267b171baabb11d8311b18
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096061"
---
# <a name="compiler-error-c2516"></a>コンパイラ エラー C2516

'name': 有効な基本クラスではありません

クラスで定義された型名から、`typedef`ステートメント。

次の例では、C2516 が生成されます。

```
// C2516.cpp
typedef unsigned long ulong;
class C : public ulong {}; // C2516
```