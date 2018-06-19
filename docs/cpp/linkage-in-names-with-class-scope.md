---
title: クラスのスコープを持つ名前にあるリンケージ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- scope [C++], linkage rules
- linkage [C++], scope linkage rules
- names [C++], scope linkage rules
- classes [C++], scope
- external linkage, scope linkage rules
- class names [C++], linkage
- classes [C++], names
- scope [C++], class names
- class scope [C++], linkage in names with
ms.assetid: 45275ff3-6e94-4967-82c8-ba540ef4da28
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9eb58f87e998fbe1eeeb9b26eb0da75046a9079d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418973"
---
# <a name="linkage-in-names-with-class-scope"></a>クラス スコープを持つ名前にあるリンケージ
クラス スコープの名前には、次のリンケージ規則が適用されます。  
  
-   静的クラス メンバーは外部リンケージを持ちます。  
  
-   クラスのメンバー関数は外部リンケージを持ちます。  
  
-   列挙子と `typedef` 名はリンケージを持ちません。  
  
 **Microsoft 固有の仕様**  
  
-   `friend` 関数として宣言された関数には、外部リンケージが必要です。 静的関数を `friend` として宣言すると、エラーが発生します。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [プログラムとリンケージ](../cpp/program-and-linkage-cpp.md)