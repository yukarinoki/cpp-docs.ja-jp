---
description: 詳細については、「インラインアセンブリでのセグメント参照」を参照してください。
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
ms.openlocfilehash: 9f9f37d7c45700358cc958f12d6f2d97da6bcf01
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122084"
---
# <a name="segment-references-in-inline-assembly"></a>インライン アセンブリでのセグメント参照

**Microsoft 固有の仕様**

名前ではなく、登録によってセグメントを参照する必要があります (セグメント名 `_TEXT` は無効です。たとえば、)。 セグメントのオーバーライドでは、ES: [BX] のように、明示的にレジスタを使用する必要があります。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__Asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
