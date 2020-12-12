---
description: '詳細情報: 偶数ディレクティブとアラインディレクティブ'
title: EVEN および ALIGN ディレクティブ
ms.date: 08/30/2018
helpviewer_keywords:
- EVEN directive
- directives, MASM
- MASM (Microsoft Macro Assembler), directives
- NOP (no operation instruction)
- ALIGN directive
ms.assetid: 7357ab2d-4a5c-43ca-accb-a5f21cdfcde5
ms.openlocfilehash: adf633e99f1cb52a7849de24751d065a0344798f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117797"
---
# <a name="even-and-align-directives"></a>EVEN および ALIGN ディレクティブ

**Microsoft 固有の仕様**

インラインアセンブラーは、ほとんどの MASM ディレクティブをサポートしていませんが、サポート `EVEN` と **配置** を行います。 これらのディレクティブは、特定の境界にラベルを配置するために必要に応じて、 **NOP** (操作なし) 命令をアセンブリコードに配置します。 これにより、一部のプロセッサに対して命令フェッチ操作の効率が向上します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__Asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
