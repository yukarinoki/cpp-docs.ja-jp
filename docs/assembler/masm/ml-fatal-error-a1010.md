---
title: ML の致命的なエラー A1010 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1010
dev_langs:
- C++
helpviewer_keywords:
- A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b622595b6994c4c4eaa74ed8f824f28dffe89b1a
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057683"
---
# <a name="ml-fatal-error-a1010"></a>ML の致命的なエラー A1010
**一致しないブロックの入れ子。**  
  
 ブロックの先頭には、対応する end がなかったか、ブロックの終了が開始に対応するありませんでした。 次のいずれかが関係している可能性があります。  
  
-   などの高度なディレクティブ[です。IF](../../assembler/masm/dot-if.md)、[です。繰り返し](../../assembler/masm/dot-repeat.md)、または[です。中に](../../assembler/masm/dot-while.md)です。  
  
-   などの条件付きアセンブリ ディレクティブ[IF](../../assembler/masm/if-masm.md)、[繰り返します](../../assembler/masm/repeat.md)、または**中**です。  
  
-   構造体または共用体の定義。  
  
-   プロシージャの定義。  
  
-   セグメントの定義。  
  
-   A [POPCONTEXT](../../assembler/masm/popcontext.md)ディレクティブです。  
  
-   条件付きのアセンブリのように、ディレクティブ、 [ELSE](../../assembler/masm/else-masm.md)、 [ELSEIF](../../assembler/masm/elseif-masm.md)、または**ENDIF**が対応する[IF](../../assembler/masm/if-masm.md)です。  
  
## <a name="see-also"></a>関連項目  
 [ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)