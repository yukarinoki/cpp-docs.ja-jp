---
title: インライン アセンブリでのセグメント参照
ms.date: 08/30/2018
helpviewer_keywords:
- references, inline assembly
- segment references in inline assembly
- inline assembly, segment references
- registers
- inline assembly, registers
- registers, inline assembly
ms.assetid: c63e6bb4-49d9-4fa1-bb22-eea21b5cbc0f
ms.openlocfilehash: 5c07fa897da23a55f376a20e7588c8c8c269d1a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577334"
---
# <a name="segment-references-in-inline-assembly"></a>インライン アセンブリでのセグメント参照

**Microsoft 固有の仕様**

名前ではなく、レジスタでは、セグメントを参照する必要があります (セグメント名`_TEXT`インスタンス有効ではない)。 セグメント オーバーライドが ES とは異なり、登録を明示的に使用する必要があります。 [BX]。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>