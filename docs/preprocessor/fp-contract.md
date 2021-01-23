---
description: pragmaMicrosoft C/c + + での fp_contract ディレクティブの詳細については、こちらを参照してください。
title: fp_contract pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.fp_contract
- fp_contract_CPP
helpviewer_keywords:
- pragma, fp_contract
- fp_contract pragma
no-loc:
- pragma
ms.openlocfilehash: 3263d1ec9675e0f8a9402ac7da78751b988e7bdf
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713650"
---
# <a name="fp_contract-no-locpragma"></a>`fp_contract` pragma

浮動小数点省略形を実行するかどうかを決定します。 浮動小数点省略形は、2つの独立した浮動小数点演算を1つの命令に結合する FMA () などの命令です。 これらの命令を使用すると、浮動小数点の精度に影響を与える可能性があります。これは、各操作の後に丸め処理を行うのではなく、両方の操作の後に1回だけラウンドを実行するため

## <a name="syntax"></a>構文

> **`#pragma fp_contract (`** { **`on`** | **`off`** } **`)`**

## <a name="remarks"></a>解説

既定で **`fp_contract`** は、は **`on`** です。 これは、可能であれば、浮動小数点の省略形命令を使用するようにコンパイラに指示します。 **`fp_contract`** 個々の **`off`** 浮動小数点命令を保持するには、をに設定します。

浮動小数点動作の詳細については、「 [ `/fp` (浮動小数点の動作の指定)](../build/reference/fp-specify-floating-point-behavior.md)」を参照してください。

その他の浮動小数点 pragma ディレクティブは次のとおりです。

- [`fenv_access`](../preprocessor/fenv-access.md)

- [`float_control`](../preprocessor/float-control.md)

## <a name="example"></a>例

このサンプルから生成されたコードでは、ターゲットプロセッサで使用可能な場合でも、追加命令が使用されません。 コメントアウトした場合 `#pragma fp_contract (off)` 、生成されたコードは、使用可能な場合は、追加された非表示命令を使用することがあります。

```cpp
// pragma_directive_fp_contract.cpp
// on x86 and x64 compile with: /O2 /fp:fast /arch:AVX2
// other platforms compile with: /O2

#include <stdio.h>

// remove the following line to enable FP contractions
#pragma fp_contract (off)

int main() {
   double z, b, t;

   for (int i = 0; i < 10; i++) {
      b = i * 5.5;
      t = i * 56.025;

      z = t * i + b;
      printf("out = %.15e\n", z);
   }
}
```

```Output
out = 0.000000000000000e+00
out = 6.152500000000000e+01
out = 2.351000000000000e+02
out = 5.207249999999999e+02
out = 9.184000000000000e+02
out = 1.428125000000000e+03
out = 2.049900000000000e+03
out = 2.783725000000000e+03
out = 3.629600000000000e+03
out = 4.587525000000000e+03
```

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
