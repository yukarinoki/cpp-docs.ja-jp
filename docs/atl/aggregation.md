---
title: 集計 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- aggregation [C++]
- aggregate objects [C++]
ms.assetid: 7125bb8e-b269-4b50-9bba-295b467a54cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ce2fbe4a2dd566541a637459510ec8422b318c47
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070919"
---
# <a name="aggregation"></a>集約

オブジェクトの実行者が、構築済みの別のオブジェクトによって提供されるサービスの利用たい場合もあります。 さらに、この 2 番目のオブジェクトが最初の一部として表示されることと思います。 COM では、両方を実現のこれらの目標を包含して集計します。

集計は、親 (外部) オブジェクトの作成プロセスの一部として含まれている (内部) オブジェクトを作成し、内部オブジェクトのインターフェイスは、外側によって公開されていることを意味します。 オブジェクトは、自身を集約可能かどうかが。 場合は、集計正常に動作するための特定のルールを従う必要があります。

主に、すべて`IUnknown`親オブジェクトに含まれているオブジェクトに対するメソッド呼び出しを委任する必要があります。

## <a name="see-also"></a>関連項目

[COM の概要](../atl/introduction-to-com.md)<br/>
[オブジェクトを再利用](/windows/desktop/com/reusing-objects)

