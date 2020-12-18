---
description: '詳細情報: Storage of Bit Fields (ビット フィールドの格納)'
title: Storage of Bit Fields (ビット フィールドの格納)
ms.date: 11/04/2016
ms.assetid: 4816a241-1580-4d1c-82ed-13d359733959
ms.openlocfilehash: 43066fe648bc380a8278168f336ebcf10cbbbdf5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205305"
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

## <a name="see-also"></a>関連項目

[構造体、共用体、列挙体、ビット フィールド](../c-language/structures-unions-enumerations-and-bit-fields.md)
