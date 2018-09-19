---
title: トークンの評価 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- tokens, evaluating
ms.assetid: 28870b62-dff6-4644-8b75-d58f340b48d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5d5c79ac043b2131df7a876f2de63922c45c9ead
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035280"
---
# <a name="evaluation-of-tokens"></a>トークンの評価

コンパイラは、トークンを解釈するときに、1 つのトークンにできる限り多くの文字を含めてから、次のトークンに進みます。 このような動作をするため、空白で正しく区切られていない場合、意図したとおりにトークンが解釈されない可能性があります。 次のような式があるとします。

```
i+++j
```

この例では、コンパイラは、3 個のプラス記号から最初に最も長い可能な演算子 (`++`) を取り出し、次に残りの正符号を加算演算子 (`+`) として処理します。 したがって、この式は `(i++) + (j)` ではなく、`(i) + (++j)` として評価されます。 この場合や同様の場合、空白とかっこを使用してあいまいさを回避し、式が適切に評価されるようにします。

**Microsoft 固有の仕様**

C コンパイラは Ctrl + Z 文字をファイル終端 (EOF) として扱います。 Ctrl + Z 以降のテキストは無視されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[C トークン](../c-language/c-tokens.md)