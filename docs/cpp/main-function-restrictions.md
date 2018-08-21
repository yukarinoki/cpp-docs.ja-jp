---
title: main 関数に関する制約 |Microsoft Docs
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
ms.openlocfilehash: 981d4c8c0ef30993811e5dbb6fd0a112a6447011
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406495"
---
# <a name="main-function-restrictions"></a>main 関数に関する制約
いくつかの制限が適用されます、**メイン**関数を他の C++ 関数には適用されません。 **メイン**関数。  
  
-   オーバー ロードできません (を参照してください[関数のオーバー ロード](function-overloading.md))。  
  
-   として宣言できません**インライン**します。  
  
-   として宣言できません**静的**します。  
  
-   そのアドレスを取得することはできません。  
  
-   呼び出すことはできません。  
  
## <a name="see-also"></a>関連項目  
 [main: プログラムの起動](../cpp/main-program-startup.md)