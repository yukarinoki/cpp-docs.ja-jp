---
title: コンパイラの警告 (レベル 1) C4651 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4651
dev_langs:
- C++
helpviewer_keywords:
- C4651
ms.assetid: f1ea82aa-4dc1-4972-b55a-57fdb962f0dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b516ef86372901d00dd20d94ed10d5e361bbab8d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099471"
---
# <a name="compiler-warning-level-1-c4651"></a>コンパイラの警告 (レベル 1) C4651

'定義' プリコンパイル済みヘッダーに定義されていますが、現在のコンパイルではありません。

プリコンパイル済みヘッダーが生成されたときに、このコンパイルではなく、定義が指定されました。

プリコンパイル済みのヘッダー内で、コードの残りの部分ではなく、定義が有効になります。

プリコンパイル済みヘッダーがで指定してビルドされている場合、コンパイラで/Yu コンパイルは指定していない場合にこの警告が生成されます。  /Yu コマンドラインに指定してを追加するには、この警告が解決されます。