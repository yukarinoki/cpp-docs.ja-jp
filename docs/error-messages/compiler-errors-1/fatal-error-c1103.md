---
title: 致命的なエラー C1103 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1103
dev_langs:
- C++
helpviewer_keywords:
- C1103
ms.assetid: 9d276939-9c47-4235-9d20-76b8434f9731
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d9e48d827c58ebf41ce3cf3862cbfbeaa494cf76
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055950"
---
# <a name="fatal-error-c1103"></a>致命的なエラー C1103

progid をインポート中の致命的なエラー: 'message'

コンパイラがタイプ ライブラリのインポートで問題を検出しました。  たとえば、progid を持つタイプ ライブラリを指定し、さらに `no_registry`を指定することはできません。

詳細については、次を参照してください。 [#import ディレクティブ](../../preprocessor/hash-import-directive-cpp.md)します。

次の例では C1103 エラーが生成されます。

```
// C1103.cpp
#import "progid:a.b.id.1.5" no_registry auto_search   // C1103
```