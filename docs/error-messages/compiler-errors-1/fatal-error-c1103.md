---
description: '詳細情報: 致命的なエラー C1103'
title: 致命的なエラー C1103
ms.date: 11/04/2016
f1_keywords:
- C1103
helpviewer_keywords:
- C1103
ms.assetid: 9d276939-9c47-4235-9d20-76b8434f9731
ms.openlocfilehash: 7e49d4f4420fc202f54a580c194244d24a4d181c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144925"
---
# <a name="fatal-error-c1103"></a>致命的なエラー C1103

progid をインポート中の致命的なエラー: 'message'

コンパイラがタイプ ライブラリのインポートで問題を検出しました。  たとえば、progid を持つタイプ ライブラリを指定し、さらに `no_registry`を指定することはできません。

詳細については、「 [#import ディレクティブ](../../preprocessor/hash-import-directive-cpp.md)」を参照してください。

次の例では C1103 エラーが生成されます。

```cpp
// C1103.cpp
#import "progid:a.b.id.1.5" no_registry auto_search   // C1103
```
