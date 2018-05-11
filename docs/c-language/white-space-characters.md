---
title: 空白文字 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- white space, characters
- characters, white space
ms.assetid: 030ccbdc-2db3-4dd0-88c8-f5c2669ddebf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec6657762a1bd896b78eea85f217ad68f887263e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="white-space-characters"></a>空白文字
スペース、タブ、改行、復帰、書式送り、垂直タブ、復帰改行の文字は、ページ出力時には単語と行を区切るスペースとして同じ目的で使用されるため、"空白文字" と呼ばれます。空白文字があると、コードが読みやすくなります。 トークンは、空白文字によって、および、演算子や句読点などの他のトークンによって区切られます。 コードを解析するとき、C コンパイラは、空白文字が区切り記号として、または、文字定数か文字列リテラルの構成要素として使用されていない限り、空白文字を無視します。 空白文字を使用してプログラムを読みやすくしてください。 コンパイラは、コメントも空白として扱います。  
  
## <a name="see-also"></a>参照  
 [C トークン](../c-language/c-tokens.md)