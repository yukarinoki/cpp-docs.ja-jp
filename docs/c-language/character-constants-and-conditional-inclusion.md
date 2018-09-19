---
title: 文字定数と条件付きの包含 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 1692207b-0707-4908-9e05-f8ed7ae0dd76
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2700d7ffa59a14e96f175e4e81933924a4bf5912
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034278"
---
# <a name="character-constants-and-conditional-inclusion"></a>文字定数と条件付きの包含

**ANSI 3.8.1** 条件付きインクルードを制御する定数式における単一文字の文字定数の値は、実行文字セットの同じ文字定数の値と一致するかどうか。 そのような文字定数は負の値を持つことができるかどうか

プリプロセッサ ステートメントで使用される文字セットは、実行文字セットと同じです。 プリプロセッサは、負の文字値も認識します。

## <a name="see-also"></a>参照

[プリプロセス ディレクティブ](../c-language/preprocessing-directives.md)