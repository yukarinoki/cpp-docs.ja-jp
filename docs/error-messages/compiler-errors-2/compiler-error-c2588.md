---
description: 詳細については、「コンパイラエラー C2588」を参照してください。
title: コンパイラ エラー C2588
ms.date: 11/04/2016
f1_keywords:
- C2588
helpviewer_keywords:
- C2588
ms.assetid: 19a0cabd-ca13-44a5-9be3-ee676abf9bc4
ms.openlocfilehash: 7f723f826a5d4e609c0766c5287a0fffdee72d18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177576"
---
# <a name="compiler-error-c2588"></a>コンパイラ エラー C2588

':: ~ identifier ': 無効なグローバルデストラクターです。

デストラクターは、クラス、構造体、または共用体以外のものに対して定義されています。 これは認められていません。

このエラーは、スコープ解決 () 演算子の左側にクラス、構造体、または共用体の名前がないことが原因で発生する可能性があり `::` ます。

次の例では、C2588 が生成されます。

```cpp
// C2588.cpp
~F();   // C2588
```
