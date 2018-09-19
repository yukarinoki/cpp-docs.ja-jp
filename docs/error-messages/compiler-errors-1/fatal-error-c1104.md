---
title: 致命的なエラー C1104 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1104
dev_langs:
- C++
helpviewer_keywords:
- C1104
ms.assetid: 45bd85c4-77d3-4d3c-b167-49c563aefb4d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e624238a1b7616ab84a655839a05cfd6899d38ea
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048111"
---
# <a name="fatal-error-c1104"></a>致命的なエラー C1104

libid をインポート中の致命的なエラー: 'message'

コンパイラがタイプ ライブラリのインポートで問題を検出しました。  たとえば、libid を持つタイプ ライブラリを指定し、さらに `no_registry`を指定することはできません。

詳細については、次を参照してください。 [#import ディレクティブ](../../preprocessor/hash-import-directive-cpp.md)します。

次の例では C1104 エラーが生成されます。

```
// C1104.cpp
#import "libid:11111111.1111.1111.1111.111111111111" version("4.0") lcid("9") no_registry auto_search   // C1104
```