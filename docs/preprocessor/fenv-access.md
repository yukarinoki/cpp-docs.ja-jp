---
title: fenv_access |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/12/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.fenv_access
- fenv_access_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, fenv_access
- fenv_access pragma
ms.assetid: 2ccea292-0ae4-42ce-9c67-cc189299857b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f74f20b1dcb20c1449d21e91181f8bfb17075b7e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="fenvaccess"></a>fenv_access

無効になります (**で**) か、または有効 (**オフ*) 浮動小数点環境に影響する最適化フラグ テストとモードの変更。

## <a name="syntax"></a>構文

> **#pragma fenv_access (** {**で** | **オフ**} **)**  

## <a name="remarks"></a>コメント

既定では、 **fenv_access**は**オフ**です。 コンパイラが想定する場合は、コードはアクセスできませんか、または浮動小数点の環境を操作し、多くの浮動小数点コードの最適化を実行できます。 設定**fenv_access**に**で**浮動小数点または環境をテストの状態フラグの例外を除き、制御モード フラグを設定するが、コードにアクセスすることをコンパイラに通知するためにします。 コンパイラでは、コードでは、浮動小数点環境を一貫してアクセスできるように、これらの最適化が無効にします。 

浮動小数点の動作の詳細については、次を参照してください。 [/fp (浮動小数点の動作を指定)](../build/reference/fp-specify-floating-point-behavior.md)です。

対象には、最適化の種類**fenv_access**は。

- グローバルの共通部分式の削除

- コードの移動

- 定数の折りたたみ

その他の浮動小数点プラグマには以下があります。

- [float_control](../preprocessor/float-control.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="examples"></a>使用例

この例では設定**fenv_access**に**で**24 ビットの精度の浮動小数点制御レジスタを設定します。

```cpp
// pragma_directive_fenv_access_x86.cpp
// compile with: /O2
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
out=9.999999776482582e-003
```

コメント アウトする場合`#pragma fenv_access (on)`前のサンプルから、コンパイラがコンパイル時の評価は、制御モードを使用しないため、出力が異なることに注意してください。

```cpp
// pragma_directive_fenv_access_2.cpp
// compile with: /O2
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
out=1.000000000000000e-002
```

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
