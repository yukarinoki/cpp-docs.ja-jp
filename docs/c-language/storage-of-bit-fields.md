---
title: ビット フィールドの格納 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 4816a241-1580-4d1c-82ed-13d359733959
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3f223ff90517b6365645a861420ebe1985f994d2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="storage-of-bit-fields"></a>Storage of Bit Fields (ビット フィールドの格納)
**ANSI 3.5.2.1** int 内のビット フィールドの割り当て順序  
  
 ビット フィールドは、整数内で最下位ビットから最上位ビットへと割り当てられます。 次のコードでは、  
  
```  
struct mybitfields  
{  
   unsigned a : 4;  
   unsigned b : 5;  
   unsigned c : 7;  
} test;  
  
int main( void )  
{  
   test.a = 2;  
   test.b = 31;  
   test.c = 0;  
}  
```  
  
 ビットは次のように配置されます。  
  
```  
00000001 11110010  
cccccccb bbbbaaaa  
```  
  
 80x86 プロセッサは整数値の下位バイトを上位バイトの前に格納するため、上記の整数 0x01F2 は、0xF2 の後ろに 0x01 が続くように物理メモリに格納されます。  
  
## <a name="see-also"></a>参照  
 [構造体、共用体、列挙体、ビット フィールド](../c-language/structures-unions-enumerations-and-bit-fields.md)