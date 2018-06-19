---
title: main 関数に関する制約 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- Main
dev_langs:
- C++
helpviewer_keywords:
- main function, restrictions on using
ms.assetid: 7b3df731-344b-44a8-850c-11cbcbfbfa83
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ed5be2df6e152b26bcade1970b35ad33655e8e02
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32419686"
---
# <a name="main-function-restrictions"></a>main 関数に関する制約
いくつかの制限を適用する、**メイン**関数を他の C++ 関数には適用されません。 **メイン**関数。  
  
-   オーバー ロードできません (を参照してください[関数のオーバー ロード](function-overloading.md))。  
  
-   として宣言することはできません**インライン**です。  
  
-   として宣言することはできません**静的**です。  
  
-   そのアドレスを取得することはできません。  
  
-   呼び出すことはできません。  
  
## <a name="see-also"></a>関連項目  
 [main: プログラムの起動](../cpp/main-program-startup.md)