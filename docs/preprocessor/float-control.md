---
title: float_control プラグマ
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.float_control
- float_control_CPP
helpviewer_keywords:
- float_control pragma
- pragmas, float_control
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
ms.openlocfilehash: aa8cdc07953405175c1753791ab53214d73ba516
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218582"
---
# <a name="float_control-pragma"></a>float_control プラグマ

関数の浮動小数点動作を指定します。

## <a name="syntax"></a>構文

> **#pragma float_control**\
> **#pragma float_control (** {**厳密** | な**strict** | **except** } **、** { **on** | **off** } **[、push]** **)** \
> **#pragma float_control (** { **push** | **pop** } **)**

## <a name="options"></a>オプション

**厳密に**は**except**、 **on** off、push |  |  | \
**精度**、**厳密**、または**except**の浮動小数点動作を指定します。 詳細については、「[/fp (浮動小数点の動作の指定)](../build/reference/fp-specify-floating-point-behavior.md)」を参照してください。 設定は、オンまたは**オフ** **に**することができます。

**Strict**の場合、 **strict**と**except**の両方の設定は、 **on**または**off**の設定によって指定されます。 **except**は on にも設定されている場合にのみ、onに設定できます。

省略可能な**プッシュ**トークンを追加すると、 **float_control**の現在の設定が内部コンパイラスタックにプッシュされます。

**押し付け**\
現在の**float_control**設定を内部コンパイラスタックにプッシュします。

**ショート**\
内部コンパイラスタックの一番上から**float_control**設定を削除し、新しい**float_control**設定を行います。

## <a name="remarks"></a>Remarks

**Except**が on の場合、 **float_control**を使用して**正確**にオフにすることはできません。 同様に、 [fenv_access](../preprocessor/fenv-access.md)が on のときは、**正確**に無効にすることはできません。 **Float_control**プラグマを使用して厳密なモデルから高速モデルに移行するには、次のコードを使用します。

```cpp
#pragma float_control(except, off)
#pragma fenv_access(off)
#pragma float_control(precise, off)
```

**Float_control**プラグマを使用して高速モデルから厳密なモデルに移行するには、次のコードを使用します。

```cpp
#pragma float_control(precise, on)
#pragma fenv_access(on)
#pragma float_control(except, on)
```

オプションが指定されていない場合、 **float_control**は無効です。

その他の浮動小数点プラグマには以下があります。

- [fenv_access](../preprocessor/fenv-access.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="example"></a>例

次の例は、プラグマ**float_control**を使用してオーバーフロー浮動小数点例外をキャッチする方法を示しています。

```cpp
// pragma_directive_float_control.cpp
// compile with: /EHa
#include <stdio.h>
#include <float.h>

double func( ) {
   return 1.1e75;
}

#pragma float_control (except, on)

int main( ) {
   float u[1];
   unsigned int currentControl;
   errno_t err;

   err = _controlfp_s(&currentControl, ~_EM_OVERFLOW, _MCW_EM);
   if (err != 0)
      printf_s("_controlfp_s failed!\n");

   try  {
      u[0] = func();
      printf_s ("Fail");
      return(1);
   }

   catch (...)  {
      printf_s ("Pass");
      return(0);
   }
}
```

```Output
Pass
```

## <a name="see-also"></a>関連項目

[プラグマディレクティブと __ プラグマキーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
