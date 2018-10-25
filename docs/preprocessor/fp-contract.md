---
title: fp_contract |Microsoft Docs
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
ms.openlocfilehash: 95f23fa132a263970047a480ccde37382b6d03de
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052165"
---
# <a name="fpcontract"></a>fp_contract

浮動小数点の省略形に配置されるかどうかを判断します。 浮動小数点の省略形は、2 つ個別浮動小数点演算に 1 つの命令を結合する (Fused Multiply-アド) FMA など命令です。 丸め処理を行う各操作後に、代わりに、プロセッサが 1 回だけ丸め両方の操作の後であるために、浮動小数点の精度を使用してこれらの手順に影響ことができます。

## <a name="syntax"></a>構文

> **#pragma fp_contract (** { **on** | **off** } **)**

## <a name="remarks"></a>Remarks

既定では、 **fp_contract**は**で**します。 これは、ように可能であれば、浮動小数点の省略形の手順を使用してコンパイラに指示します。 設定**fp_contract**に**オフ**個々 の浮動小数点命令を維持します。

浮動小数点の動作の詳細については、次を参照してください。 [/fp (浮動小数点の動作の指定)](../build/reference/fp-specify-floating-point-behavior.md)します。

その他の浮動小数点プラグマには以下があります。

- [fenv_access](../preprocessor/fenv-access.md)

- [float_control](../preprocessor/float-control.md)

## <a name="example"></a>例

このサンプルから生成されたコードでは、ターゲット プロセッサで使用可能な場合にも組み合わされ、-乗算-追加の命令は使用しません。 コメント アウトする場合`#pragma fp_contract (off)`、入手可能になった場合、生成されたコードが組み合わされ、-乗算-追加の命令を使用可能性があります。

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
