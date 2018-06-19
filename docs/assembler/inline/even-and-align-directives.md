---
title: EVEN および ALIGN ディレクティブ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: a43425a4038ffb140eeaa0a9d111a39fc5c11ff0
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057956"
---
# <a name="even-and-align-directives"></a>EVEN および ALIGN ディレクティブ
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 では、インライン アセンブラーは、ほとんどの MASM ディレクティブをサポートしない、`EVEN`と**ALIGN**です。 これらのディレクティブを配置**NOP** (操作なし)、アセンブリ コードを特定の境界にラベルを配置に必要な手順です。 これにより、いくつかのプロセッサ命令フェッチ操作がより効率的にします。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)