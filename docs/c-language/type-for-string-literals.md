---
title: 文字列リテラルの型 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- string literals, type
- types [C], string literals
ms.assetid: f50a28af-20c1-4440-bdc6-564c86a309c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7773882d6fb04341a6f6d3a2cbcfda1d05f85d17
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063282"
---
# <a name="type-for-string-literals"></a>文字列リテラルの型

文字列リテラルは、`char` の型配列 (つまり、**char[ ]**) を持ちます  (ワイド文字列は、`wchar_t` の型配列 (つまり、**wchar_t[ ]**) を持ちます)。これは、文字列が型 `char` の要素の配列であることを意味しています。 配列の要素の数は、文字列の文字の数に 1 (終端の null 文字) を足した数と同じです。

## <a name="see-also"></a>参照

[C 文字列リテラル](../c-language/c-string-literals.md)