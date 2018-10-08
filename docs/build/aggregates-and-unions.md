---
title: 集約と共用体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- aggregates [C++], and unions
ms.assetid: 859fc211-b111-4f12-af98-de78e48f9b92
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aac6da94a0786e5cdc2eee4d16f5927f66e0a8d5
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2018
ms.locfileid: "48861188"
---
# <a name="aggregates-and-unions"></a>集約と共用体

配列、構造体、共用体などの他の種類では、一貫性のある集約と共用体ストレージとデータ取得を保証するより厳密なのアラインメント要件があります。 配列、構造、および共用体の定義を次に示します。

- 配列

   連続するデータ オブジェクトの順序付きのグループが含まれています。 各オブジェクトには、要素は呼び出されます。 配列内のすべての要素と同じサイズとデータ型であります。

- 構造体

   データ オブジェクトの順序付きのグループが含まれています。 、配列の要素とは異なり、構造内のデータ オブジェクトは別のデータの種類とサイズを持つことができます。 構造体の各データ オブジェクトには、メンバーが呼び出されます。

- 和集合

   名前付きのメンバーのセットのいずれかを保持するオブジェクト。 名前付きセットのメンバーは、任意の型指定できます。 共用体に割り当てられたストレージは、その共用体、および配置に必要なすべての埋め込みの最大のメンバーに必要なストレージと同じです。

次の表では、厳密に推奨されるスカラー共用体と構造体のメンバーの配置を示します。

||||
|-|-|-|
|スカラー型|C データ型|必要な配置|
|**INT8**|**char**|Byte|
|**UINT8**|**unsigned char**|Byte|
|**INT16**|**short**|Word|
|**UINT16**|**unsigned short**|Word|
|**INT32**|**int**、**長**|ダブルワード|
|**UINT32**|**符号なし int、unsigned long**|ダブルワード|
|**INT64**|**__int64**|Quadword|
|**UINT64**|**unsigned __int64**|Quadword|
|**FP32 (単一の有効桁数)**|**float**|ダブルワード|
|**FP64 (有効桁数を 2 倍)**|**double**|Quadword|
|**ポインター**|<strong>\*</strong>|Quadword|
|**__m64**|**構造体の _ _m64**|Quadword|
|**__m128**|**_ _m128 の構造体**|Octaword|

次の集計の配置ルールが適用されます。

- 配列の配置では、配列の要素の 1 つの配置と同じです。

- 構造体または共用体の先頭の配置は、個々 のメンバーの最大の配置です。 構造体または共用体の各メンバーは、前のメンバーによって、暗黙の型の内部の埋め込みが必要ですが、前の表で定義されている、適切なアラインメントに配置する必要があります。

- 構造体のサイズは、その配置では、最後のメンバーの後にスペースを必要がありますの整数倍である必要があります。 構造体と共用体は、配列でグループ化できる、ので、構造体または共用体の配列の各要素の最初し、最後に、以前に判断する適切な配置。

- 以前のルールを管理する限り、アラインメント要件より大きくなるようにデータを配置することになります。

- 個々 のコンパイラでは、サイズ上の理由から、構造体のパッキングを調整できます。 たとえば[/Zp (構造体メンバーの配置)](../build/reference/zp-struct-member-alignment.md)構造体のパッキングを調整できます。

## <a name="see-also"></a>関連項目

[型とストレージ](../build/types-and-storage.md)
