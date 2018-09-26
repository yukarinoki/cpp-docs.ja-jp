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
ms.openlocfilehash: 3aa487ee277954470cdd8b16f9f64f465c195897
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055703"
---
# <a name="white-space-characters"></a>空白文字

スペース、タブ、改行、復帰、書式送り、垂直タブ、復帰改行の文字は、ページ出力時には単語と行を区切るスペースとして同じ目的で使用されるため、"空白文字" と呼ばれます。空白文字があると、コードが読みやすくなります。 トークンは、空白文字によって、および、演算子や句読点などの他のトークンによって区切られます。 コードを解析するとき、C コンパイラは、空白文字が区切り記号として、または、文字定数か文字列リテラルの構成要素として使用されていない限り、空白文字を無視します。 空白文字を使用してプログラムを読みやすくしてください。 コンパイラは、コメントも空白として扱います。

## <a name="see-also"></a>参照

[C トークン](../c-language/c-tokens.md)