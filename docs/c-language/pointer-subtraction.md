---
title: ポインターの減算 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- pointer subtraction
ms.assetid: 4d515690-088a-43f6-bb8c-57b849f7ccf7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 576a8d9252db3d5733775a7a0c348b428462aa0f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="pointer-subtraction"></a>ポインターの減算
**ANSI 3.3.6, 4.1.1** 同じ配列の要素への 2 つのポインター間の差を保持するために必要な整数型、**ptrdiff_t**  
  
 `ptrdiff_t` は、32 ビット x86 プラットフォームでは `int` です。 64 ビット プラットフォームでは、`ptrdiff_t` typedef は `__int64` です。
  
## <a name="see-also"></a>参照  
 [配列とポインター](../c-language/arrays-and-pointers.md)
