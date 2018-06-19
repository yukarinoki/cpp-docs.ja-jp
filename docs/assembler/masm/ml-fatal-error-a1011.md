---
title: ML の致命的なエラー A1011 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1011
dev_langs:
- C++
helpviewer_keywords:
- A1011
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 843d676cba61e0da5f917a48408e56e79abb9efd
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057209"
---
# <a name="ml-fatal-error-a1011"></a>ML の致命的なエラー A1011
**ディレクティブは、コントロール ブロックである必要があります。**  
  
 アセンブラーがいずれかのない、必要な高度なディレクティブが見つかりました。 次のディレクティブのいずれかが検出されました。  
  
-   [.ELSE](../../assembler/masm/dot-else.md)せず[です。もし](../../assembler/masm/dot-if.md)  
  
-   [.ENDIF](../../assembler/masm/dot-endif.md)せず[です。もし](../../assembler/masm/dot-if.md)  
  
-   [.ENDW](../../assembler/masm/dot-endw.md)せず[です。WHILE](../../assembler/masm/dot-while.md)  
  
-   [.UNTILCXZ](../../assembler/masm/dot-untilcxz.md) without [.REPEAT](../../assembler/masm/dot-repeat.md)  
  
-   [.続行](../../assembler/masm/dot-continue.md)せず[です。中に](../../assembler/masm/dot-while.md)または[です。繰り返し](../../assembler/masm/dot-repeat.md)  
  
-   [.中断](../../assembler/masm/dot-break.md)せず[です。中に](../../assembler/masm/dot-while.md)または[です。繰り返し](../../assembler/masm/dot-repeat.md)  
  
-   [.ELSE](../../assembler/masm/dot-else.md)以下 `.ELSE`  
  
## <a name="see-also"></a>関連項目  
 [ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)