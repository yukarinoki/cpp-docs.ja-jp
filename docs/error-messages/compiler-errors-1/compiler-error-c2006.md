---
title: コンパイラ エラー C2006 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2006
dev_langs:
- C++
helpviewer_keywords:
- C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9468be17584a54047563bace2b35f5cb4888b41
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031211"
---
# <a name="compiler-error-c2006"></a>コンパイラ エラー C2006

'directive' が 'token' が見つかりません、ファイル名が必要です。

などのディレクティブ[#include](../../preprocessor/hash-include-directive-c-cpp.md)または[#import](../../preprocessor/hash-import-directive-cpp.md)ファイル名が必要です。 エラーを解決することを確認します*トークン*が有効なファイル名。 また、二重引用符や山かっこでファイル名を配置します。

次の例では、C2006 が生成されます。

```
// C2006.cpp
#include stdio.h   // C2006
```

考えられる解決方法:

```
// C2006b.cpp
// compile with: /c
#include <stdio.h>
```