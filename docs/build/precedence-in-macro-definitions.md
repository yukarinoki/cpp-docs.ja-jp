---
title: マクロ定義内の優先度 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, precedence in macro definitions
- macros, precedence
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ce6f0acc898dc719d2252d5cc59dff92bda4a98
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368614"
---
# <a name="precedence-in-macro-definitions"></a>マクロ定義の優先順位
マクロは、複数の定義を持つ、NMAKE は最も高い優先順位の定義を使用します。 次に、最上位から最下位からの優先順位の順序を示します。  
  
1.  コマンドラインで定義されているマクロ  
  
2.  マクロはメイクファイルで定義されているか、ファイルを含める  
  
3.  継承の環境変数マクロ  
  
4.  Tools.ini ファイルで定義されているマクロ  
  
5.  定義済みマクロなど[CC](../build/command-macros-and-options-macros.md)と[AS](../build/command-macros-and-options-macros.md)  
  
 /E を使用して、同じ名前のメイクファイルのマクロをオーバーライドする環境変数から継承されたマクロが発生します。 使用して **!UNDEF**をコマンド ラインをオーバーライドします。  
  
## <a name="see-also"></a>関連項目  
 [NMAKE マクロの定義](../build/defining-an-nmake-macro.md)