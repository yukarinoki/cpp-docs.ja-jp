---
title: EVEN および ALIGN ディレクティブ |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
f1_keywords:
- align
- EVEN
dev_langs:
- C++
helpviewer_keywords:
- EVEN directive
- directives, MASM
- MASM (Microsoft Macro Assembler), directives
- NOP (no operation instruction)
- ALIGN directive
ms.assetid: 7357ab2d-4a5c-43ca-accb-a5f21cdfcde5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06a1007c50e3490e5b14e4da886494557be0d37e
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43688302"
---
# <a name="even-and-align-directives"></a>EVEN および ALIGN ディレクティブ

**Microsoft 固有の仕様**

では、インライン アセンブラーがほとんどの MASM ディレクティブをサポートしていませんが`EVEN`と**ALIGN**します。 これらのディレクティブを配置**NOP** (操作なし)」の手順には、アセンブリのコードを特定の境界にラベルを配置するために必要とします。 これにより、一部のプロセッサの命令フェッチ操作がより効率的にします。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>