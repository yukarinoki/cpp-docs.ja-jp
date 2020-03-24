---
title: リンカー ツールの警告 LNK4022
ms.date: 11/04/2016
f1_keywords:
- LNK4022
helpviewer_keywords:
- LNK4022
ms.assetid: 890f487e-db98-45dd-a226-c7ccead82b1e
ms.openlocfilehash: 9b9ce09a7133c0bdc18957f6ade213583e9540eb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194188"
---
# <a name="linker-tools-warning-lnk4022"></a>リンカー ツールの警告 LNK4022

シンボル ' symbol ' に対して一意の一致が見つかりません

リンクまたは LIB で、指定された非装飾シンボルに対して複数の一致が見つかりました。あいまいさを解決できませんでした。 出力ファイル (.exe、.dll、.exp、.lib) は生成されません。 この警告の後には、重複するシンボルごとに1つの警告[LNK4002](../../error-messages/tool-errors/linker-tools-warning-lnk4002.md)が続き、最後に致命的なエラー [LNK1152](../../error-messages/tool-errors/linker-tools-error-lnk1152.md)が続きます。

この警告を回避するには、装飾形式で記号を指定します。 装飾名を表示するには、オブジェクトに対して[DUMPBIN](../../build/reference/dumpbin-options.md)を実行します。
