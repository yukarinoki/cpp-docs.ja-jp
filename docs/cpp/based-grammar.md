---
title: __based 文法
ms.date: 11/04/2016
helpviewer_keywords:
- based addressing
ms.assetid: a68ff750-c7fa-4c0c-8d5f-2df76e4686c5
ms.openlocfilehash: 8dec9b0bcc7db25e2ec4c39b9d907922691bfc05
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558146"
---
# <a name="based-grammar"></a>__based 文法

## <a name="microsoft-specific"></a>Microsoft 固有の仕様

ベースとなるアドレス指定は、オブジェクトが割り当てられるセグメントを詳細に制御する必要がある場合に便利です (静的および動的ベースのデータ)。

または、32 ビットまたは 64 ビット ベースへの 32 ビットまたは 64 ビットの変位を含む、に基づいて型を定義するのみに基づいて、フォーム ベース アドレスの 32 ビットおよび 64 ビット コンパイルで許容されるが"ポインター" **void**します。

## <a name="grammar"></a>文法

*基づく範囲修飾子*: **_ _based (***ベース式***)** 

*ベース式*: *based-variablebased-abstract-declaratorsegment-namesegment-cast*

*ベース変数*:*識別子*

*ベースの抽象宣言*:*抽象宣言子*

*基本型*:*型名*

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[Based ポインター](../cpp/based-pointers-cpp.md)