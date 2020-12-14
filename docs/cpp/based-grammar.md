---
description: '詳細情報: __based 文法'
title: __based 文法
ms.date: 11/04/2016
helpviewer_keywords:
- based addressing
ms.assetid: a68ff750-c7fa-4c0c-8d5f-2df76e4686c5
ms.openlocfilehash: 9c449c45700c57d0c6f6018ca47e40d42c4b2ad0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304520"
---
# <a name="__based-grammar"></a>__based 文法

**Microsoft 固有の仕様**

ベースとなるアドレス指定は、オブジェクトが割り当てられるセグメントを詳細に制御する必要がある場合に便利です (静的および動的ベースのデータ)。

32ビットと64ビットのコンパイルで許容されるベースアドレスの唯一の形式は、32ビットベースまたは64ビットベースへの32ビットまたは64ビットの変位を含む型を定義する "ポインターに基づく" というものです **`void`** 。

## <a name="grammar"></a>文法

*based-範囲-修飾子*: **__based (**  *基本式*  **)**

*基本式*: *based-declaratorsegment-namesegment--cast*

*ベース変数*: *識別子*

*based-abstract-宣言子*: *abstract-宣言* 子

*基本型*: *type-name*

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[ベースポインター](../cpp/based-pointers-cpp.md)
