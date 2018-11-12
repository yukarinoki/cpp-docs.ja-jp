---
title: アドレスの格納
ms.date: 11/04/2016
helpviewer_keywords:
- storage [C++], addresses
- addresses [C++], storage of
ms.assetid: 423b2402-b847-4788-ad70-943b7c9c5c8b
ms.openlocfilehash: 2a0e218d4d34fa1482986ecccd7da8adba38086b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539374"
---
# <a name="storage-of-addresses"></a>アドレスの格納

アドレスに必要なストレージの量およびアドレスの意味は、コンパイラの実装によって異なります。 異なる型へのポインターが同じ長さを持つという保証はありません。 したがって、**sizeof(char \*)** は **sizeof(int \*)** と必ずしも同じではありません。

**Microsoft 固有の仕様**

Microsoft C コンパイラでは、**sizeof(char \*)** は **sizeof(int \*)** と同じです。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[ポインター宣言](../c-language/pointer-declarations.md)