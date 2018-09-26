---
title: char 型 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- type char
- unsigned char keyword [C]
- char keyword [C]
ms.assetid: a5da0866-e780-4793-be87-15a8426e7ea0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eec964d9b81ee93f888bbd4152f06f6bdf51b6d0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053831"
---
# <a name="type-char"></a>char 型

`char` 型は、表現できる文字セットのメンバーの整数値を格納するために使用されます。 この整数値は、特定の文字に対応する ASCII コードです。

**Microsoft 固有の仕様**

`unsigned char` 型の文字値の範囲は、16 進数で 0 から 0xFF までです。 **signed char** には 0x80 から 0x7F までの範囲があります。 これらの範囲は、0 から 255 の 10 進数と -128 から +127 の 10 進数にそれぞれ変換されます。 /J コンパイラ オプションは、既定値を **signed** から `unsigned` に変更します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[基本型の格納](../c-language/storage-of-basic-types.md)