---
title: コンパイラ エラー C2014 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2014
dev_langs:
- C++
helpviewer_keywords:
- C2014
ms.assetid: 231d8e9c-48c0-4027-99a3-245d186275ec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4a9167d71e717490b89c1861abe9a9da9e0ab6a8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064855"
---
# <a name="compiler-error-c2014"></a>コンパイラ エラー C2014

プリプロセッサ コマンドは、最初の空白として起動する必要があります。

`#`プリプロセッサ ディレクティブの記号が空白でない行の最初の文字にする必要があります。

次の例では、C2014 が生成されます。

```
// C2014.cpp
int k; #include <stdio.h>   // C2014
```

考えられる解決方法:

```
// C2014b.cpp
// compile with: /c
int k;
#include <stdio.h>
```