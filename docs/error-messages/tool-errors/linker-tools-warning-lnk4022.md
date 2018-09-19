---
title: リンカー ツールの警告 LNK4022 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4022
dev_langs:
- C++
helpviewer_keywords:
- LNK4022
ms.assetid: 890f487e-db98-45dd-a226-c7ccead82b1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 644e7a9ba26dab15e2bfa2a269f62c04f0510180
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041000"
---
# <a name="linker-tools-warning-lnk4022"></a>リンカー ツールの警告 LNK4022

シンボル 'symbol' の一意の一致を見つけることができません。

指定された装飾されていないシンボルのリンクまたは LIB が複数見つかりましたが一致して、あいまいさが解決できませんでした。 出力ファイル (.exe、.dll、.exp、または .lib) は生成されません。 この警告は、1 つの警告の後に[LNK4002](../../error-messages/tool-errors/linker-tools-warning-lnk4002.md)ごとのシンボルを複製し、致命的なエラーが最後に[LNK1152](../../error-messages/tool-errors/linker-tools-error-lnk1152.md)します。

この警告を回避するには、修飾された形式で、シンボルを指定します。 実行[DUMPBIN](../../build/reference/dumpbin-options.md)装飾名のオブジェクトを参照してください。