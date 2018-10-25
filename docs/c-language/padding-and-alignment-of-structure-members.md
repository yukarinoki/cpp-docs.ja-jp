---
title: 構造体メンバーの埋め込みとアライメント | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- structure members, padding and alignment
ms.assetid: c999820b-dd47-41fc-b923-e4c7ebbcd30f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a1b301372a9998197c46c1e44c91c9d3456cea8e
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808213"
---
# <a name="padding-and-alignment-of-structure-members"></a>Padding and Alignment of Structure Members (構造体メンバーのパディングとアラインメント)

**ANSI 3.5.2.1** 構造体のメンバーの埋め込みとアラインメント、およびビット フィールドがストーレジ単位境界をまたげるかどうか

構造体メンバーは、宣言されている順に格納され、最初のメンバーが最も下位のメモリ アドレスを、最後のメンバーが最も上位のアドレスを持ちます。

データ オブジェクトにはそれぞれ、alignment-requirement (アラインメント要件) があります。 構造体、共用体、配列を除くすべてのデータのアラインメント要件は、オブジェクトのサイズまたは現在のパッキング サイズです (パッキング サイズは /Zp または `pack` プラグマで指定され、いずれか小さい方が適用されます)。 構造体、共用体、配列の場合、アラインメント要件はそのメンバーの最大のアラインメント要件になります。 すべてのオブジェクトには、次の式を満たすように offset (オフセット) が割り当てられます。

*offset* **%** *alignment-requirement* **== 0**

隣接するビット フィールドは、同じサイズの整数型で、次のビット フィールドがビット フィールドの共通のアラインメント要件によって課される境界を越えずに現在の割り当て単位に収まる場合は、同じ 1、2、または 4 バイトの割り当て単位にパックされます。

## <a name="see-also"></a>参照

[構造体、共用体、列挙体、ビット フィールド](../c-language/structures-unions-enumerations-and-bit-fields.md)