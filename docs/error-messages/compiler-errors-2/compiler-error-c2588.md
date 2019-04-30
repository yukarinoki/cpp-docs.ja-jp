---
title: コンパイラ エラー C2588
ms.date: 11/04/2016
f1_keywords:
- C2588
helpviewer_keywords:
- C2588
ms.assetid: 19a0cabd-ca13-44a5-9be3-ee676abf9bc4
ms.openlocfilehash: 15f9ba62751d9b3cb17ab56659310292dab41adf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350453"
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