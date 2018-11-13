---
title: Storage of Bit Fields (ビット フィールドの格納)
ms.date: 11/04/2016
ms.assetid: 4816a241-1580-4d1c-82ed-13d359733959
ms.openlocfilehash: 7aa6e02c347ff14bb0552320567b343c7215ebc7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499088"
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