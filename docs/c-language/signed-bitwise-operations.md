---
title: Signed Bitwise Operations (符号付きビット処理演算) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- bitwise operations
- signed bitwise operations
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 184fd5a0e6c12cb58e9fed759459e7b8172896f8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038298"
---
# <a name="signed-bitwise-operations"></a>Signed Bitwise Operations (符号付きビット処理演算)

**ANSI 3.3** 符号付き整数のビットごとの演算の結果

符号付き整数のビットごとの演算は、符号なし整数のビットごとの演算と同じように動作します。 たとえば、`-16 & 99` は、バイナリでは次のように表されます。

```
  11111111 11110000
& 00000000 01100011
  _________________
  00000000 01100000
```

ビットごとの AND の結果は 96 です。

## <a name="see-also"></a>参照

[整数](../c-language/integers.md)