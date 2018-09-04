---
title: インライン アセンブリで参照をセグメント化 |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- references, inline assembly
- segment references in inline assembly
- inline assembly, segment references
- registers
- inline assembly, registers
- registers, inline assembly
ms.assetid: c63e6bb4-49d9-4fa1-bb22-eea21b5cbc0f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 792dda60407928aaf4a7d3fec2a61c0018b8b35a
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43676390"
---
# <a name="segment-references-in-inline-assembly"></a>インライン アセンブリでのセグメント参照

**Microsoft 固有の仕様**

名前ではなく、レジスタでは、セグメントを参照する必要があります (セグメント名`_TEXT`インスタンス有効ではない)。 セグメント オーバーライドが ES とは異なり、登録を明示的に使用する必要があります。 [BX]。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>