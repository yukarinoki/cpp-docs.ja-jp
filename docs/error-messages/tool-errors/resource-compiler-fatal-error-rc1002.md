---
title: リソース コンパイラの致命的なエラー RC1002 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC1002
dev_langs:
- C++
helpviewer_keywords:
- RC1002
ms.assetid: b43dfece-0dc3-4d0b-9d8f-509699b9ae80
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d54f49b7cce988c5902a01142efe061ba03e424
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114528"
---
# <a name="resource-compiler-fatal-error-rc1002"></a>リソース コンパイラの致命的なエラー RC1002

ヒープ スペースがありません。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. Windows のスワップ ファイルの領域を増やします。 スワップ ファイルの領域を増やす方法の詳細については、Windows のヘルプ内の仮想メモリを参照してください。

1. 小さなファイルに、現在のファイルに分割し、個別にコンパイルします。

1. その他のプログラムまたはシステムで実行されているドライバーを削除します。