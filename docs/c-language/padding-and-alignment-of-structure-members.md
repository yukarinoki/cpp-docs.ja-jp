---
description: '詳細情報: Padding and Alignment of Structure Members (構造体メンバーのパディングとアラインメント)'
title: Padding and Alignment of Structure Members (構造体メンバーのパディングとアラインメント)
ms.date: 10/18/2018
helpviewer_keywords:
- structure members, padding and alignment
ms.assetid: c999820b-dd47-41fc-b923-e4c7ebbcd30f
ms.openlocfilehash: db2530ecb00e5a01f5d10ff45da55420a8139be0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137450"
---
# <a name="padding-and-alignment-of-structure-members"></a>Padding and Alignment of Structure Members (構造体メンバーのパディングとアラインメント)

**ANSI 3.5.2.1** 構造体のメンバーの埋め込みとアラインメント、およびビット フィールドがストーレジ単位境界をまたげるかどうか

構造体メンバーは、宣言されている順に格納され、最初のメンバーが最も下位のメモリ アドレスを、最後のメンバーが最も上位のアドレスを持ちます。

データ オブジェクトにはそれぞれ、alignment-requirement (アラインメント要件) があります。 構造体、共用体、配列を除くすべてのデータのアラインメント要件は、オブジェクトのサイズまたは現在のパッキング サイズです (パッキング サイズは /Zp または `pack` プラグマで指定され、いずれか小さい方が適用されます)。 構造体、共用体、配列の場合、アラインメント要件はそのメンバーの最大のアラインメント要件になります。 すべてのオブジェクトには、次の式を満たすように offset (オフセット) が割り当てられます。

*offset* **%** *alignment-requirement* **== 0**

隣接するビット フィールドは、同じサイズの整数型で、次のビット フィールドがビット フィールドの共通のアラインメント要件によって課される境界を越えずに現在の割り当て単位に収まる場合は、同じ 1、2、または 4 バイトの割り当て単位にパックされます。

## <a name="see-also"></a>関連項目

[構造体、共用体、列挙体、ビット フィールド](../c-language/structures-unions-enumerations-and-bit-fields.md)
