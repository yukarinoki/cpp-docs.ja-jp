---
title: fenv_access pragma
description: Fenv_access ディレクティブの使用法と効果について説明し pragma ます。 Fenv_access ディレクティブは、実行時に浮動小数点環境へのアクセスを制御します。
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.fenv_access
- fenv_access_CPP
helpviewer_keywords:
- pragma, fenv_access
- fenv_access pragma
no-loc:
- pragma
ms.openlocfilehash: be33bbf9de381850ec78ece204d117ebc537152b
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713663"
---
# <a name="fenv_access-no-locpragma"></a>`fenv_access` pragma

**`on`** **`off`** 浮動小数点環境フラグのテストとモードの変更を変更する可能性のある () または最適化 () を無効にします。

## <a name="syntax"></a>構文

> **`#pragma fenv_access (`** { **`on`** | **`off`** } **`)`**

## <a name="remarks"></a>解説

既定で **`fenv_access`** は、は **`off`** です。 コンパイラは、コードが浮動小数点環境にアクセスしたり操作したりしないことを前提としています。 環境へのアクセスが必要ない場合、コンパイラは浮動小数点コードを最適化するためにさらに多くのことを行うことができます。

**`fenv_access`** コードが浮動小数点の状態フラグ、例外、またはコントロールモードフラグの設定をテストする場合に有効にします。 コンパイラは、浮動小数点の最適化を無効にして、コードが常に浮動小数点環境にアクセスできるようにします。

[/Fp: strict] コマンドラインオプションを使用すると、が自動的に有効になり **`fenv_access`** ます。 このとその他の浮動小数点動作の詳細については、「 [/fp (Floating-Point 動作の指定)](../build/reference/fp-specify-floating-point-behavior.md)」を参照してください。

を **`fenv_access`** pragma 他の浮動小数点の設定と組み合わせて使用する方法には、次のような制限があります。

- **`fenv_access`** 正確なセマンティクスが有効になっていない限り、を有効にすることはできません。 正確なセマンティクスは、で有効にすることも、 [`float_control`](float-control.md) pragma [`/fp:precise`](../build/reference/fp-specify-floating-point-behavior.md) またはコンパイラオプションを使用して有効にすることもでき [`/fp:strict`](../build/reference/fp-specify-floating-point-behavior.md) ます。 **`/fp:precise`** 他の浮動小数点コマンドラインオプションが指定されていない場合、コンパイラは既定でになります。

- を設定するときに、を使用して **`float_control`** 正確なセマンティクスを無効にすることはできません **`fenv_access(on)`** 。

の対象となる最適化の種類は次のとおりです **`fenv_access`** 。

- グローバルの共通部分式の削除

- コードの移動

- 定数の折りたたみ

その他の浮動小数点 pragma ディレクティブは次のとおりです。

- [float_control](../preprocessor/float-control.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="examples"></a>例

次の例では **`fenv_access`** 、をに設定して **`on`** 、24ビット精度の浮動小数点制御レジスタを設定します。

```cpp
// pragma_directive_fenv_access_x86.cpp
// compile with: /O2 /arch:IA32
// processor: x86
#include <stdio.h>
#include <float.h>
#include <errno.h>
#pragma fenv_access (on)

int main() {
   double z, b = 0.1, t = 0.1;
   unsigned int currentControl;
   errno_t err;

   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);
   if (err != 0) {
      printf_s("The function _controlfp_s failed!\n");
      return -1;
   }
   z = b * t;
   printf_s ("out=%.15e\n",z);
}
```

```Output
out=9.999999776482582e-03
```

前のサンプルからコメントアウトすると、 `#pragma fenv_access (on)` 出力は異なります。 これは、コンパイラがコンパイル時の評価を行うためです。この評価では、制御モードは使用されません。

```cpp
// pragma_directive_fenv_access_2.cpp
// compile with: /O2 /arch:IA32
#include <stdio.h>
#include <float.h>

int main() {
   double z, b = 0.1, t = 0.1;
   unsigned int currentControl;
   errno_t err;

   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);
   if (err != 0) {
      printf_s("The function _controlfp_s failed!\n");
      return -1;
   }
   z = b * t;
   printf_s ("out=%.15e\n",z);
}
```

```Output
out=1.000000000000000e-02
```

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
