---
title: リンカ ツール エラー LNK1277 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1277
dev_langs:
- C++
helpviewer_keywords:
- LNK1277
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 542c48bd23b3f84ab301404987c77d964f51823e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082532"
---
# <a name="linker-tools-error-lnk1277"></a>リンカ ツール エラー LNK1277

オブジェクトのレコードが pgd (ファイル名) に見つかりませんでした。

使用する場合[/LTCG:PGOPTIMZE](../../build/reference/ltcg-link-time-code-generation.md)、入力の .lib、def、または .obj ファイルのいずれかのパスは/LTCG:PGINSTRUMENT 中に検出されたパスから異なっていました。 これは、/LTCG:PGINSTRUMENT 後に、LIB 環境変数での変更説明可能性があります。 入力ファイルへの完全パスは、.pgd ファイルに格納されます。

/LTCG:PGOPTIMIZE では、入力が/LTCG:PGINSTRUMENT フェーズと一致させることが必要です。

この警告を解決するには、次のいずれかの操作を行います。

- /LTCG:PGINSTRUMENT を実行し、すべてのテストの実行を再実行/LTCG:PGOPTIMIZE を実行します。

- /LTCG:PGINSTRUMENT を実行したときに、LIB 環境変数を変更します。

LNK1277 周囲/LTCG:PGUPDATE を使用して操作することは推奨されません。