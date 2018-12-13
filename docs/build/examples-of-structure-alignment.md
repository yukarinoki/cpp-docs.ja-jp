---
title: 構造体の配置例
ms.date: 11/19/2018
helpviewer_keywords:
- structure alignment
- examples [C++], structure alignment
ms.assetid: 03d137bf-5cc4-472e-9583-6498f2534199
ms.openlocfilehash: 7c4b3ae29674e9c4fc27e8e175867339001b9a0d
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2018
ms.locfileid: "52175341"
---
# <a name="examples-of-structure-alignment"></a>構造体の配置例

次の 4 つ例では、配置済みの構造体または共用体、および対応する数値は、その構造体または共用メモリ内のレイアウトを示しています。 を宣言します。 図内の各列は、メモリのバイトを表し、列の数がそのバイトの移動距離を示します。 各図の 2 行目の名前は、宣言内の変数の名前に対応します。 影付きの列には、指定された配置を実現するために必要なは埋め込みが示されます。

## <a name="example-1"></a>例 1

```C
// Total size = 2 bytes, alignment = 2 bytes (word).

_declspec(align(2)) struct {
    short a;      // +0; size = 2 bytes
}
```

![AMD 変換例 1 の構造体レイアウト](../build/media/vcamd_conv_ex_1_block.png "AMD 変換例 1 の構造体レイアウト")

## <a name="example-2"></a>例 2

```C
// Total size = 24 bytes, alignment = 8 bytes (quadword).

_declspec(align(8)) struct {
    int a;       // +0; size = 4 bytes
    double b;    // +8; size = 8 bytes
    short c;     // +16; size = 2 bytes
}
```

![AMD 変換例 2 の構造体レイアウト](../build/media/vcamd_conv_ex_2_block.png "AMD 変換例 2 の構造体レイアウト")

## <a name="example-3"></a>例 3

```C
// Total size = 22 bytes, alignment = 4 bytes (doubleword).

_declspec(align(4)) struct {
    char a;       // +0; size = 1 byte
    short b;      // +2; size = 2 bytes
    char c;       // +4; size = 1 byte
    int d;        // +8; size = 4 bytes
}
```

![AMD 変換例 2 の構造体レイアウト](../build/media/vcamd_conv_ex_3_block.png "AMD 変換例 2 の構造体レイアウト")

## <a name="example-4"></a>例 4

```C
// Total size = 8 bytes, alignment = 8 bytes (quadword).

_declspec(align(8)) union {
    char *p;      // +0; size = 8 bytes
    short s;      // +0; size = 2 bytes
    long l;       // +0; size = 4 bytes
}
```

![AMD 変換例 4 の共用体 layouit](../build/media/vcamd_conv_ex_4_block.png "AMD 変換例 4 の共用体 layouit")

## <a name="see-also"></a>関連項目

[型とストレージ](../build/types-and-storage.md)<br/>
