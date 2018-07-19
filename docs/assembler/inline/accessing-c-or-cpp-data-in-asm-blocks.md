---
title: C または C++ _ _asm ブロック内のデータにアクセスする |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data members [C++], in __asm blocks
- data access [C++], in __asm blocks
- __asm keyword [C++], data members
- structure types in __asm blocks
ms.assetid: e99f5a28-0381-4090-8ece-6af8f2436a49
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9631db3c09c19e38791a6c909be02acd1c91601b
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32049760"
---
# <a name="accessing-c-or-c-data-in-asm-blocks"></a>__asm ブロックの C または C++ のデータへのアクセス
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 インライン アセンブラーの非常に便利では、C または C++ の変数を名前で参照する機能です。 `__asm`ブロックは、ブロックが表示されるスコープ内にある変数の名前も含め、シンボルを参照できます。 インスタンスの場合は、C 変数`var`命令スコープ内にあります。  
  
```  
__asm mov eax, var  
```  
  
 値が格納`var`EAX にします。  
  
 クラス、構造体、または共用体のメンバーに一意の名前がある場合、`__asm`ブロックは、変数を指定することがなく、メンバーの名前のみを使用して参照できますまたは`typedef`期間の前に名前 (**.**) 演算子。 メンバー名が一意でない場合は、ただし、する必要があります配置変数または`typedef`期間の演算子の直前の名前。 次のサンプル共有で構造体の型など、`same_name`メンバー名として: です。  
  
 型と変数を宣言する場合  
  
```  
struct first_type hal;  
struct second_type oat;  
```  
  
 すべての参照メンバーを`same_name`ために、変数名を使用する必要があります`same_name`一意ではありません。 メンバーが、`weasel`メンバー名のみを使用して参照できるように、一意の名前を持ちます。  
  
```  
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
  
 変数名を省略することがコーディング便宜だけであることに注意してください。 変数の名前があるかどうか、同じアセンブリ命令が生成されます。  
  
 アクセスの制限に関係なく C++ でのデータ メンバーにアクセスできます。 ただし、関数メンバーを呼び出すことはできません。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [__asm ブロックでの C または C++ の使用](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)