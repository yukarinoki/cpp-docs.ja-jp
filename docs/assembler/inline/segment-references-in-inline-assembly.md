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
ms.openlocfilehash: 865fc5fac5f46cdc8c55966e9989227d1d671d6f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169254"
---
# <a name="segment-references-in-inline-assembly"></a>インライン アセンブリでのセグメント参照

**Microsoft 固有の仕様**

名前ではなく、登録によってセグメントを参照する必要があります (たとえば、セグメント名 `_TEXT` が無効であるなど)。 セグメントのオーバーライドでは、ES: [BX] のように、明示的にレジスタを使用する必要があります。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
