---
title: リソース コンパイラの致命的なエラー RW1022 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW1022
dev_langs:
- C++
helpviewer_keywords:
- RW1022
ms.assetid: 6747c8a9-9c9b-4422-b414-0645d22092d0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: caaefc045a31ca64aa9843927d550ef66285cb2e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099850"
---
# <a name="resource-compiler-fatal-error-rw1022"></a>リソース コンパイラの致命的なエラー RW1022

**ファイルの書き込み I/O エラー**

リソース コンパイラは、ファイルに書き込めませんでした。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. ディスク領域が不足しています。 空き領域を作成する実行可能ファイルのサイズの 2 倍以上でなければなりません。

1. ボリュームが読み取り専用です。

1. 正しくないセクターです。

1. 共有違反です。