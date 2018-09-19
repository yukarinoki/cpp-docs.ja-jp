---
title: リンカ ツール エラー LNK1201 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1201
dev_langs:
- C++
helpviewer_keywords:
- LNK1201
ms.assetid: 64c3f496-a428-4b54-981e-faa82ef9c8a1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c133748f95846160e1387e31e023d9ce459b281
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055271"
---
# <a name="linker-tools-error-lnk1201"></a>リンカ ツール エラー LNK1201

プログラム データベース 'filename'; への書き込みエラーディスク領域の不足、無効なパス、または十分な特権の確認します。

リンクは、出力ファイルのプログラム データベース (PDB) に書き込めませんでした。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. ファイルが壊れています。 PDB ファイルと再リンクを削除します。

1. ファイルの書き込みにディスク領域が不足します。

1. ドライブは、ネットワークの問題の可能性があるため、ご利用いただけません。

1. デバッガーがリンクをプログラム上でアクティブにします。

1. ヒープ領域にします。  参照してください[C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md)詳細についてはします。