---
title: Intel&#39;s MMX 命令セット |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: c054c1236fbbc74cfc45834f05aa2be08faa07f6
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32050738"
---
# <a name="intel39s-mmx-instruction-set"></a>Intel&#39;s MMX 命令セット
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 Visual C コンパイラでは、Intel の MMX (マルチ メディア拡張機能) の命令が、インライン アセンブラーのセットを使用することができます。 MMX 命令もサポートしていますデバッガー逆アセンブルします。 関数は、MMX 命令が含まれていますが、マルチ メディアの状態を空に EMMS 命令が含まれていない場合、コンパイラは警告メッセージを生成します。 詳細については、Intel の Web サイトを参照してください。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)