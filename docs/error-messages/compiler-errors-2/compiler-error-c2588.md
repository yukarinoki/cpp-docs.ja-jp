---
title: コンパイラ エラー C2588
ms.date: 11/04/2016
f1_keywords:
- C2588
helpviewer_keywords:
- C2588
ms.assetid: 19a0cabd-ca13-44a5-9be3-ee676abf9bc4
ms.openlocfilehash: 15f9ba62751d9b3cb17ab56659310292dab41adf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596782"
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