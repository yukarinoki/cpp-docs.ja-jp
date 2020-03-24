---
title: EVEN および ALIGN ディレクティブ
ms.date: 08/30/2018
helpviewer_keywords:
- EVEN directive
- directives, MASM
- MASM (Microsoft Macro Assembler), directives
- NOP (no operation instruction)
- ALIGN directive
ms.assetid: 7357ab2d-4a5c-43ca-accb-a5f21cdfcde5
ms.openlocfilehash: b191ce0942d7596090bfd7948a37a5c9e6aac15e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169436"
---
# <a name="even-and-align-directives"></a>EVEN および ALIGN ディレクティブ

**Microsoft 固有の仕様**

インラインアセンブラーは、ほとんどの MASM ディレクティブをサポートしていませんが、`EVEN` と**アラ**インをサポートしています。 これらのディレクティブは、特定の境界にラベルを配置するために必要に応じて、 **NOP** (操作なし) 命令をアセンブリコードに配置します。 これにより、一部のプロセッサに対して命令フェッチ操作の効率が向上します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
