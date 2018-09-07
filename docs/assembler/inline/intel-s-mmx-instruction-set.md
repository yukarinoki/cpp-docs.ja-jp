---
title: Intel&#39;s MMX 命令セット |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- MMX instruction set
ms.assetid: 705deb2d-c3fd-4696-9e22-8bcf25866daf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 95f3cb57fc5c046057a5efa568ce930f13ca3256
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43688354"
---
# <a name="intel39s-mmx-instruction-set"></a>Intel&#39;s MMX 命令セット

**Microsoft 固有の仕様**

Visual C コンパイラでは、Intel の MMX (マルチ メディア拡張機能) の命令が、インライン アセンブラーのセットを使用できます。 MMX 命令は、デバッガーの逆アセンブリによってもサポートされます。 関数は、MMX 命令が含まれていますが、マルチ メディアの状態を空に EMMS 命令が含まれていない場合、コンパイラは警告メッセージを生成します。 詳細については、Intel の Web サイトを参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>