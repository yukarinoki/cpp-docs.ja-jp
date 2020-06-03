---
title: __asm ブロックの C または C++ のデータへのアクセス
ms.date: 08/30/2018
helpviewer_keywords:
- data members [C++], in __asm blocks
- data access [C++], in __asm blocks
- __asm keyword [C++], data members
- structure types in __asm blocks
ms.assetid: e99f5a28-0381-4090-8ece-6af8f2436a49
ms.openlocfilehash: b4341f87226118906749dcdb18b9227e68be6a23
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318089"
---
# <a name="accessing-c-or-c-data-in-__asm-blocks"></a>__asm ブロックの C または C++ のデータへのアクセス

**マイクロソフト固有**

インライン アセンブリの大きな便利な方法は、C または C++ 変数を名前で参照できることです。 ブロック`__asm`は、ブロックが出現するスコープ内にある変数名を含む任意のシンボルを参照できます。 たとえば、C 変数`var`がスコープ内にある場合、命令は

```cpp
__asm mov eax, var
```

の値を`var`EAX に格納します。

クラス、構造体、または共用体のメンバーが一意の名前を`__asm`持つ場合、ブロックは、ピリオド (**.**) 演算子の`typedef`前に変数または名前を指定しなくても、メンバー名のみを使用して参照できます。 ただし、メンバー名が固有でない場合は、変数または`typedef`名前をピリオド演算子の直前に置く必要があります。 たとえば、次のサンプルの構造体型は、メンバー`same_name`名として共有されます。

型を使用して変数を宣言する場合

```cpp
struct first_type hal;
struct second_type oat;
```

メンバー`same_name`へのすべての参照は、一意ではないため`same_name`、変数名を使用する必要があります。 ただし、メンバー`weasel`には一意の名前が付いているため、メンバー名のみを使用して参照できます。

```cpp
// InlineAssembler_Accessing_C_asm_Blocks.cpp
// processor: x86
#include <stdio.h>
struct first_type
{
   char *weasel;
   int same_name;
};

struct second_type
{
   int wonton;
   long same_name;
};

int main()
{
   struct first_type hal;
   struct second_type oat;

   __asm
   {
      lea ebx, hal
      mov ecx, [ebx]hal.same_name ; Must use 'hal'
      mov esi, [ebx].weasel       ; Can omit 'hal'
   }
   return 0;
}
```

変数名を省略することは、単なるコーディングの利便性に過ぎないことに注意してください。 変数名が存在するかどうかにかかわらず、同じアセンブリ命令が生成されます。

C++ のデータ メンバーには、アクセス制限に関係なくアクセスできます。 ただし、メンバー関数を呼び出すことはできません。

**エンド マイクロソフト 固有**

## <a name="see-also"></a>関連項目

[__asm ブロックでの C または C++ の使用](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>
