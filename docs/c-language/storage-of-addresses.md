---
description: '詳細情報: アドレスの格納'
title: アドレスの格納
ms.date: 11/04/2016
helpviewer_keywords:
- storage [C++], addresses
- addresses [C++], storage of
ms.assetid: 423b2402-b847-4788-ad70-943b7c9c5c8b
ms.openlocfilehash: 8f0b51370659d7a23739d75f53492d171c17e422
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97296694"
---
# <a name="storage-of-addresses"></a>アドレスの格納

アドレスに必要なストレージの量およびアドレスの意味は、コンパイラの実装によって異なります。 異なる型へのポインターが同じ長さを持つという保証はありません。 したがって、**sizeof(char \*)** は **sizeof(int \*)** と必ずしも同じではありません。

**Microsoft 固有の仕様**

Microsoft C コンパイラでは、**sizeof(char \*)** は **sizeof(int \*)** と同じです。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[ポインター宣言](../c-language/pointer-declarations.md)
