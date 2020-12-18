---
description: '詳細情報: Signed Bitwise Operations (符号付きビット処理演算)'
title: Signed Bitwise Operations (符号付きビット処理演算)
ms.date: 11/04/2016
helpviewer_keywords:
- bitwise operations
- signed bitwise operations
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
ms.openlocfilehash: 98cca4d7450e0b65301ba3d2ad65f0cb3aca81ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97292651"
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

## <a name="see-also"></a>関連項目

[整数](../c-language/integers.md)
