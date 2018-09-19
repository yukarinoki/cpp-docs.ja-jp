---
title: コンパイラの警告 (レベル 4) C4235 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4235
dev_langs:
- C++
helpviewer_keywords:
- C4235
ms.assetid: d4214799-d62c-4674-b4e2-9e201c303303
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c9e709017e51101efe53a8697bb145014f200871
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031822"
---
# <a name="compiler-warning-level-4-c4235"></a>コンパイラの警告 (レベル 4) C4235

非標準の拡張機能が使用されています : 'キーワード' キーワードはこのアーキテクチャではサポートされていません

使用したキーワードは、サポートされていません。

この警告は、自動的にエラーになります。 この動作を変更する場合を使用して、 [#pragma warning](../../preprocessor/warning.md)します。 たとえば、C4235 でレベル 2 の警告を発行させるには、

```
#pragma warning(2:4235)
```

をソース コード ファイルに追加します。