---
title: 数値演算エラー M6201 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6201
dev_langs:
- C++
helpviewer_keywords:
- M6201
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 87d2c09d6448bcf7fb0557fa3a174c60205a34ea
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099396"
---
# <a name="math-error-m6201"></a>数値演算エラー M6201

'function': (_d) エラー

指定された関数の引数は、その関数の有効な入力値のドメイン外でした。

## <a name="example"></a>例

```
result = sqrt(-1.0)   // C statement
result = SQRT(-1.0)   !  FORTRAN statement
```

このエラーが、`_matherr`関数、関数名、引数、およびエラーの種類を使用します。 書き直すことができます、`_matherr`特定の実行時の浮動小数点数値演算エラーの処理をカスタマイズする関数。