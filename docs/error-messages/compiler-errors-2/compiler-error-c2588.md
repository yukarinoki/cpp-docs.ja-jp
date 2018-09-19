---
title: コンパイラ エラー C2588 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2588
dev_langs:
- C++
helpviewer_keywords:
- C2588
ms.assetid: 19a0cabd-ca13-44a5-9be3-ee676abf9bc4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d656dbde06d6052fd10611675f2cff8818cdb6e5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46108574"
---
# <a name="compiler-error-c2588"></a>コンパイラ エラー C2588

':: ~ identifier': 無効なグローバル デストラクター

デストラクターは、クラス、構造体または共用体以外のものに対して定義されます。 これは認められていません。

このエラーは、不足しているクラス、構造、またはスコープ解決演算子の左側にある共用体の名前によって発生することができます (`::`) 演算子。

次の例では、C2588 が生成されます。

```
// C2588.cpp
~F();   // C2588
```