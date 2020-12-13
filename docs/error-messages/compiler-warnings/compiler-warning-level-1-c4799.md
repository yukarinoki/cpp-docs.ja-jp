---
description: '詳細情報: コンパイラの警告 (レベル 1) C4799'
title: コンパイラの警告 (レベル 1) C4799
ms.date: 11/04/2016
f1_keywords:
- C4799
helpviewer_keywords:
- C4799
ms.assetid: 8ecbd06f-c778-4371-a2fb-c690b6743ec8
ms.openlocfilehash: 9bfa84791a713d5ed5c0382402b958c255e30521
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334932"
---
# <a name="compiler-warning-level-1-c4799"></a>コンパイラの警告 (レベル 1) C4799

> 関数 '*function*' の最後に emm がありません

関数には、少なくとも1つの MMX 命令がありますが、命令がありません `EMMS` 。 マルチメディア命令を使用する場合 `EMMS` は、 `_mm_empty` MMX コードの最後でマルチメディアタグワードをクリアするために、命令または組み込みも使用する必要があります。

Ivec を使用するときに C4799 が発生する可能性があります。これは、コードがを返す前に、EMM 命令を正しく実行しないことを示しています。 これは、これらのヘッダーに対しては偽の警告です。 IVEC で _SILENCE_IVEC_C4799 を定義することで、これらをオフにすることができます。 ただし、この場合もコンパイラがこの型の正しい警告を提供しないことに注意してください。

関連情報については、「 [Intel の MMX 命令セット](../../assembler/inline/intel-s-mmx-instruction-set.md)」を参照してください。
