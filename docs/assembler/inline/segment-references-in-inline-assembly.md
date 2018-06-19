---
title: インライン アセンブリで参照をセグメント化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: f7add95852f751ed29dad8e0ba9577abd55fabaf
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32051477"
---
# <a name="segment-references-in-inline-assembly"></a>インライン アセンブリでのセグメント参照
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 名前ではなくレジスタでは、セグメントを参照する必要があります (セグメント名`_TEXT`が有効でないインスタンス)。 セグメント オーバーライドが ES と同様に、登録を明示的に、使用する必要があります。 [BX] です。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)