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
ms.openlocfilehash: 63fa73988b9b9433a988035789a923ac73936214
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79441581"
---
# <a name="even-and-align-directives"></a>EVEN および ALIGN ディレクティブ

**Microsoft 固有の仕様**

インラインアセンブラーは、ほとんどの MASM ディレクティブをサポートしていませんが、`EVEN` と**アラ**インをサポートしています。 これらのディレクティブは、特定の境界にラベルを配置するために必要に応じて、 **NOP** (操作なし) 命令をアセンブリコードに配置します。 これにより、一部のプロセッサに対して命令フェッチ操作の効率が向上します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>