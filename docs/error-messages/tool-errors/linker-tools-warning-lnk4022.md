---
description: 詳細については、「リンカーツールの警告 LNK4022」を参照してください。
title: リンカー ツールの警告 LNK4022
ms.date: 11/04/2016
f1_keywords:
- LNK4022
helpviewer_keywords:
- LNK4022
ms.assetid: 890f487e-db98-45dd-a226-c7ccead82b1e
ms.openlocfilehash: f0f968bf8e562d87e2227fb67f7a37b450c813b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331940"
---
# <a name="linker-tools-warning-lnk4022"></a>リンカー ツールの警告 LNK4022

シンボル ' symbol ' に対して一意の一致が見つかりません

リンクまたは LIB で、指定された非装飾シンボルに対して複数の一致が見つかりました。あいまいさを解決できませんでした。 出力ファイル (.exe、.dll、.exp、.lib) は生成されません。 この警告の後には、重複するシンボルごとに1つの警告 [LNK4002](../../error-messages/tool-errors/linker-tools-warning-lnk4002.md) が続き、最後に致命的なエラー [LNK1152](../../error-messages/tool-errors/linker-tools-error-lnk1152.md)が続きます。

この警告を回避するには、装飾形式で記号を指定します。 装飾名を表示するには、オブジェクトに対して [DUMPBIN](../../build/reference/dumpbin-options.md) を実行します。
