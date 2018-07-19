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
ms.openlocfilehash: 3114f1ef379495f36f4231dbad6fd41ac145bcfe
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37941747"
---
# <a name="main-function-restrictions"></a>main 関数に関する制約
いくつかの制限が適用されます、`main`関数を他の C++ 関数には適用されません。 `main`関数。  
  
-   オーバー ロードできません (を参照してください[関数のオーバー ロード](function-overloading.md))。  
  
-   として宣言できません**インライン**します。  
  
-   として宣言できません**静的**します。  
  
-   そのアドレスを取得することはできません。  
  
-   呼び出すことはできません。  
  
## <a name="see-also"></a>関連項目  
 [main: プログラムの起動](../cpp/main-program-startup.md)