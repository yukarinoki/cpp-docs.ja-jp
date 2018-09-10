---
title: コンテキストの属性 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++/CLI], contexts
ms.assetid: 3086351f-77a8-4048-99e9-3b6b041b9437
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0e3935b168220b528afaecd2e1438cfe49496b1b
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313664"
---
# <a name="attribute-contexts"></a>属性コンテキスト
C++ 属性は、次の 4 つの基本的なフィールドを使用して記述できます: に適用できますターゲット (**適用先**) 場合は、反復可能かどうか (**Repeatable**)、その他の属性 (の存在を必要な**必要な属性**)、およびその他の属性の非互換性 (**無効な属性**)。 これらのフィールドは、各属性の参照トピックの表に表示されます。 これらの各フィールドについて、次に示します。
  
## <a name="applies-to"></a>対象
 このフィールドには、指定した属性の有効な対象となっているさまざまな C++ 言語要素について説明します。 たとえば、属性で"class"を指定する場合、**適用先**フィールド、属性は、有効な C++ クラスにのみ適用できますこれを示します。 属性はクラスのメンバー関数に適用する場合、構文エラーが発生します。
  
 詳細については、次を参照してください。[属性を使用して](../windows/attributes-by-usage.md)します。
  
## <a name="repeatable"></a>反復可能
 このフィールドは、同じターゲットに属性を繰り返し適用するかどうかを示します。 属性の大半は、反復可能はありません。
  
## <a name="required-attributes"></a>必要な属性
 このフィールドに表示されるその他の属性が必要な適切に機能する指定した属性のある (つまり、同じターゲットに適用される)。 このフィールドのすべてのエントリが存在する属性の一般的なことはできません。
  
## <a name="invalid-attributes"></a>無効な属性
 このフィールドは、指定した属性と互換性があるその他の属性を一覧表示します。 このフィールドのすべてのエントリが存在する属性の一般的なことはできません。
  
## <a name="see-also"></a>関連項目
 [C++ 属性リファレンス](../windows/cpp-attributes-reference.md)