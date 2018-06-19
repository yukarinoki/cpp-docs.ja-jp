---
title: ML の致命的なエラー A1007 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1007
dev_langs:
- C++
helpviewer_keywords:
- A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10b883fad01943cd8cff71b3da9dee66407ccc93
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32055730"
---
# <a name="ml-fatal-error-a1007"></a>ML の致命的なエラー A1007
**入れ子のレベルが深すぎます**  
  
 アセンブラーでは、その入れ子の上限に達しました。 制限は、特に記載のない以外のレベルを 20 です。  
  
 次のいずれかの入れ子が深すぎます。  
  
-   などの高度なディレクティブ[です。IF](../../assembler/masm/dot-if.md)、[です。繰り返し](../../assembler/masm/dot-repeat.md)、または[です。中に](../../assembler/masm/dot-while.md)です。  
  
-   構造体の定義。  
  
-   条件付きアセンブリ ディレクティブです。  
  
-   プロシージャの定義。  
  
-   A [PUSHCONTEXT](../../assembler/masm/pushcontext.md)ディレクティブ (上限は 10)。  
  
-   セグメントの定義。  
  
-   インクルード ファイル。  
  
-   このマクロは。  
  
## <a name="see-also"></a>関連項目  
 [ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)