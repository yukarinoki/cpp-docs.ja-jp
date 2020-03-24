---
title: コンパイラの警告 (レベル 1) C4799
ms.date: 11/04/2016
f1_keywords:
- C4799
helpviewer_keywords:
- C4799
ms.assetid: 8ecbd06f-c778-4371-a2fb-c690b6743ec8
ms.openlocfilehash: ec92da425718cd5ddc579d1d733a0bc4e56dc04a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175104"
---
# <a name="compiler-warning-level-1-c4799"></a>コンパイラの警告 (レベル 1) C4799

> 関数 '*function*' の最後に emm がありません

関数には、少なくとも1つの MMX 命令がありますが、`EMMS` 命令がありません。 マルチメディア命令を使用する場合は、`EMMS` 命令または `_mm_empty` 組み込みを使用して、MMX コードの最後でマルチメディアタグワードをクリアする必要もあります。

Ivec を使用するときに C4799 が発生する可能性があります。これは、コードがを返す前に、EMM 命令を正しく実行しないことを示しています。 これは、これらのヘッダーに対しては偽の警告です。 IVEC で _SILENCE_IVEC_C4799 を定義することで、これらをオフにすることができます。 ただし、この場合もコンパイラがこの型の正しい警告を提供しないことに注意してください。

関連情報については、「 [Intel の MMX 命令セット](../../assembler/inline/intel-s-mmx-instruction-set.md)」を参照してください。
