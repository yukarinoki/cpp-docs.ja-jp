---
title: アドレスの格納
ms.date: 11/04/2016
helpviewer_keywords:
- storage [C++], addresses
- addresses [C++], storage of
ms.assetid: 423b2402-b847-4788-ad70-943b7c9c5c8b
ms.openlocfilehash: 47b09ab6cd0b2045206daaee4badad32858ff934
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62336193"
---
# <a name="storage-of-addresses"></a>アドレスの格納

アドレスに必要なストレージの量およびアドレスの意味は、コンパイラの実装によって異なります。 異なる型へのポインターが同じ長さを持つという保証はありません。 したがって、**sizeof(char \*)** は **sizeof(int \*)** と必ずしも同じではありません。

**Microsoft 固有の仕様**

Microsoft C コンパイラでは、**sizeof(char \*)** は **sizeof(int \*)** と同じです。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[ポインター宣言](../c-language/pointer-declarations.md)
