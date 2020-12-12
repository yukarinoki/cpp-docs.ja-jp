---
description: 詳細については、__asm ブロックでの C または C++ データへのアクセス
title: __asm ブロックの C または C++ のデータへのアクセス
ms.date: 08/30/2018
helpviewer_keywords:
- data members [C++], in __asm blocks
- data access [C++], in __asm blocks
- __asm keyword [C++], data members
- structure types in __asm blocks
ms.assetid: e99f5a28-0381-4090-8ece-6af8f2436a49
ms.openlocfilehash: b24d25b5687dd309c400b17c1e0eb6b35ef986f2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118083"
---
# <a name="accessing-c-or-c-data-in-__asm-blocks"></a>__asm ブロックの C または C++ のデータへのアクセス

**Microsoft 固有の仕様**

インラインアセンブリの優れた利便性は、C または C++ の変数を名前で参照できることです。 ブロックは、 **`__asm`** ブロックが表示されているスコープ内の任意のシンボル (変数名を含む) を参照できます。 たとえば、C 変数 `var` がスコープ内にある場合、命令

```cpp
__asm mov eax, var
```

の値を `var` EAX に格納します。

クラス、構造体、または共用体のメンバーに一意の名前がある場合、ブロックは、 **`__asm`** **`typedef`** ピリオド (**.**) 演算子の前に変数または名前を指定せずに、メンバー名のみを使用して参照できます。 ただし、メンバー名が一意でない場合は、変数または名前をピリオド演算子の直前に配置する必要があり **`typedef`** ます。 たとえば、次の例では、という名前の構造体が `same_name` メンバー名として共有されています。

型を使用して変数を宣言する場合

```cpp
struct first_type hal;
struct second_type oat;
```

が一意ではないため、メンバーへのすべての参照で `same_name` 変数名を使用する必要があり `same_name` ます。 ただし、メンバーには `weasel` 一意の名前が付いているため、メンバー名のみを使用して参照できます。

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

変数名の省略は単なるコーディングの便宜であることに注意してください。 変数名が存在するかどうかにかかわらず、同じアセンブリ命令が生成されます。

アクセス制限に関係なく、C++ のデータメンバーにアクセスできます。 ただし、メンバー関数を呼び出すことはできません。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__Asm ブロックでの C または C++ の使用](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>
