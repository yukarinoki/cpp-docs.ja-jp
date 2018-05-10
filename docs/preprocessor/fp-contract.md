---
title: fp_contract |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/12/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.fp_contract
- fp_contract_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, fp_contract
- fp_contract pragma
ms.assetid: 15b97338-6680-4287-ba2a-2dccc5b2ccf5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 514b4708129d625ea7880e4c61be22c4b1ac2db5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="fpcontract"></a>fp_contract

浮動小数点の省略形が配置を受け取るかどうかを判断します。 浮動小数点の省略形は、2 つ別々 浮動小数点演算に 1 つの命令を結合する (Fused Multiply-追加) FMA などの命令です。 これらの手順を使用できます丸め処理を行う各操作後に、代わりに、プロセッサが 1 回だけ丸め両方の操作後にあるために、浮動小数点の精度に影響します。

## <a name="syntax"></a>構文

> **#pragma fp_contract (** { **on** | **off** } **)**  

## <a name="remarks"></a>コメント  

既定では、 **fp_contract**は**で**です。 これは、浮動小数点の縮小の手順を使用可能な限り、コンパイラを示しています。 設定**fp_contract**に**オフ**個々 の浮動小数点命令を維持します。

浮動小数点の動作の詳細については、次を参照してください。 [/fp (浮動小数点の動作を指定)](../build/reference/fp-specify-floating-point-behavior.md)です。

その他の浮動小数点プラグマには以下があります。

- [fenv_access](../preprocessor/fenv-access.md)

- [float_control](../preprocessor/float-control.md)

## <a name="example"></a>例

このサンプルから生成されたコードでは、ターゲット プロセッサで使用可能な場合でも、: fused multiply-追加の命令は使用しません。 コメント アウトする場合`#pragma fp_contract (off)`、使用可能になる場合、生成されたコードが: fused multiply-追加の命令を使用して可能性があります。  
  
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

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
