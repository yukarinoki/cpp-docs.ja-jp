---
title: fenv_access プラグマ
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.fenv_access
- fenv_access_CPP
helpviewer_keywords:
- pragmas, fenv_access
- fenv_access pragma
ms.assetid: 2ccea292-0ae4-42ce-9c67-cc189299857b
ms.openlocfilehash: c8e66881bde12df28bf24e18230471cb4caca792
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218597"
---
# <a name="fenv_access-pragma"></a>fenv_access プラグマ

浮動小数点環境フラグのテストおよびモードの変更を変更できる最適化を無効 (**on**) または有効 (**オフ**) にします。

## <a name="syntax"></a>構文

> **#pragma fenv_access (** { **on** | **off** } **)**

## <a name="remarks"></a>Remarks

既定では、 **fenv_access**は**オフ**になっています。 コードが浮動小数点環境にアクセスしたり操作したりしないことをコンパイラが想定できる場合は、多くの浮動小数点コードの最適化を実行できます。 **Fenv_access**を**on**に設定すると、コードが浮動小数点環境にアクセスして状態フラグや例外をテストしたり、制御モードフラグを設定したりすることをコンパイラに通知します。 コンパイラは、コードが常に浮動小数点環境にアクセスできるように、これらの最適化を無効にします。

浮動小数点の動作の詳細については、「 [/fp (浮動小数点の動作の指定)](../build/reference/fp-specify-floating-point-behavior.md)」を参照してください。

**Fenv_access**の対象となる最適化の種類は次のとおりです。

- グローバルの共通部分式の削除

- コードの移動

- 定数の折りたたみ

その他の浮動小数点プラグマには以下があります。

- [float_control](../preprocessor/float-control.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="examples"></a>使用例

この例では、 **fenv_access**を**on**に設定して、24ビット精度の浮動小数点制御レジスタを設定します。

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

前のサンプルから`#pragma fenv_access (on)`コメントアウトした場合は、コンパイラがコンパイル時の評価を行い、制御モードを使用しないため、出力が異なることに注意してください。

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

[プラグマディレクティブと __ プラグマキーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
