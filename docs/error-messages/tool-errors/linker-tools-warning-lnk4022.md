---
title: リンカー ツールの警告 LNK4022 |Microsoft ドキュメント
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
ms.openlocfilehash: cffb9c4c67bc3003b8dcdda0ad3a2e8d55abe932
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300372"
---
# <a name="linker-tools-warning-lnk4022"></a>リンカー ツールの警告 LNK4022
シンボル 'symbol' の一意の一致を見つけることができません。  
  
 リンクまたは LIB が複数検出に指定された装飾されていないシンボルの一致して、に関して、あいまいさが解決できませんでした。 出力ファイル (.exe、.dll、.exp、または .lib) は生成されません。 この警告の 1 つの警告が続く[LNK4002](../../error-messages/tool-errors/linker-tools-warning-lnk4002.md)ごとのシンボルを複製し、致命的なエラーが最後に[LNK1152](../../error-messages/tool-errors/linker-tools-error-lnk1152.md)です。  
  
 この警告を回避するのには、修飾された形式で、シンボルを指定します。 実行[DUMPBIN](../../build/reference/dumpbin-options.md)装飾名のオブジェクトを参照してください。