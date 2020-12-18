---
description: '詳細情報: ポインターの減算'
title: ポインターの減算
ms.date: 11/04/2016
helpviewer_keywords:
- pointer subtraction
ms.assetid: 4d515690-088a-43f6-bb8c-57b849f7ccf7
ms.openlocfilehash: a2f5c252ad61cd990d6f890431a8d3107f303a75
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195893"
---
# <a name="pointer-subtraction"></a>ポインターの減算

**ANSI 3.3.6, 4.1.1** 同じ配列の要素への 2 つのポインター間の差を保持するために必要な整数型、**ptrdiff_t**

`ptrdiff_t` は、32 ビット x86 プラットフォームでは **`int`** です。 64 ビット プラットフォームでは、`ptrdiff_t` typedef は **`__int64`** です。

## <a name="see-also"></a>関連項目

[配列とポインター](../c-language/arrays-and-pointers.md)
