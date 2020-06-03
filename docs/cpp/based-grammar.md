---
title: __based 文法
ms.date: 11/04/2016
helpviewer_keywords:
- based addressing
ms.assetid: a68ff750-c7fa-4c0c-8d5f-2df76e4686c5
ms.openlocfilehash: 149439c82780f12669e5a3180f975c573ed30422
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181409"
---
# <a name="__based-grammar"></a>__based 文法

**Microsoft 固有の仕様**

ベースとなるアドレス指定は、オブジェクトが割り当てられるセグメントを詳細に制御する必要がある場合に便利です (静的および動的ベースのデータ)。

32ビットと64ビットのコンパイルで許容されるベースアドレスの唯一の形式は、32ビットまたは64ビットベースへの32ビットまたは64ビットの変位を含む型を定義する、または**void**に基づく、"ポインターに基づく" ということです。

## <a name="grammar"></a>文法

*based-範囲-修飾子*: **__based (**  *基本式*  **)**

*基本式*: *based-declaratorsegment-namesegment--cast*

*ベース変数*:*識別子*

*based-abstract-宣言子*: *abstract-宣言*子

*基本型*: *type-name*

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[Based ポインター](../cpp/based-pointers-cpp.md)
