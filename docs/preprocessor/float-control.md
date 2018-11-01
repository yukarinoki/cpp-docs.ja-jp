---
title: float_control
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.float_control
- float_control_CPP
helpviewer_keywords:
- float_control pragma
- pragmas, float_control
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
ms.openlocfilehash: 63e27e992778776e186345da07937d1a88844e5d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611017"
---
# <a name="floatcontrol"></a>float_control

関数の浮動小数点動作を指定します。

## <a name="syntax"></a>構文

> **#pragma float_control** [ **(** [*値* **、** *設定***[、プッシュ]** |[**プッシュ** | **pop** ] **)** ]

## <a name="options"></a>オプション

*値*、*設定*[、**プッシュ**]<br/>
浮動小数点の動作を指定します。 *値*できる**正確な**、 **strict**、または**を除く**します。 詳細については、「[/fp (浮動小数点の動作の指定)](../build/reference/fp-specify-floating-point-behavior.md)」を参照してください。 *設定*できます**で**または**オフ**します。

場合*値*は**strict**、両方の設定**strict**と**を除く**で指定された*設定*. **除く**にしか設定できません**で**とき**正確な**または**厳密な**にも設定されている**で**します。

場合、省略可能な**プッシュ**トークンは追加、現在の設定*値*内部コンパイラ スタックにプッシュされます。

**push**<br/>
現在のプッシュ**float_control**内部コンパイラ スタックに設定

**pop**<br/>
削除、 **float_control**内部コンパイラ スタックの一番上から設定し、それは新しい**float_control**設定。

## <a name="remarks"></a>Remarks

使用することはできません**float_control**に**正確な**オフのときに**を除く**にします。 同様に、**正確な**ときにオフにすることはできません[fenv_access](../preprocessor/fenv-access.md)にします。 使用して高速モデルに厳格なモデルから移動する、 **float_control**プラグマを使用して、次のコード。

```cpp
#pragma float_control(except, off)
#pragma fenv_access(off)
#pragma float_control(precise, off)
```

高速モデルから厳格なモデルに移行する、 **float_control**プラグマを使用して、次のコード。

```cpp
#pragma float_control(precise, on)
#pragma fenv_access(on)
#pragma float_control(except, on)
```

オプションが指定されていない場合**float_control**も何も起こりません。

その他の浮動小数点プラグマには以下があります。

- [fenv_access](../preprocessor/fenv-access.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="example"></a>例

次の例は、プラグマを使用してオーバーフロー浮動小数点例外をキャッチする方法を示しています。 **float_control**します。

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

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
