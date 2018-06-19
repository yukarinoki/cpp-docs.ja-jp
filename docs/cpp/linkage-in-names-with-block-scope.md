---
title: ブロック スコープを持つ名前にあるリンケージ |Microsoft ドキュメント
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
- block scope [C++]
- external linkage, scope linkage rules
ms.assetid: 73efa91a-f761-47f7-bbd9-9f9e3508e218
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ab7758e962c028c4746836e470ee43eaab510f9e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418888"
---
# <a name="linkage-in-names-with-block-scope"></a>ブロック スコープを持つ名前にあるリンケージ
次のリンケージ規則はブロック スコープの名前に適用されます (ローカル名)。  
  
-   として宣言された名前`extern`として既に宣言されている場合を除き、外部リンケージを持ちます**静的**です。  
  
-   ブロック スコープを持つ他のすべての名前にはリンケージがありません。  
  
## <a name="see-also"></a>関連項目  
 [プログラムとリンケージ](../cpp/program-and-linkage-cpp.md)