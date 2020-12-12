---
description: '詳細情報: 集計'
title: 集計
ms.date: 11/04/2016
helpviewer_keywords:
- aggregation [C++]
- aggregate objects [C++]
ms.assetid: 7125bb8e-b269-4b50-9bba-295b467a54cc
ms.openlocfilehash: fb02dd399020f8768fcdb3cc86687578e51cb3ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166097"
---
# <a name="aggregation"></a>集計

オブジェクトの実装が、事前に構築された別のオブジェクトによって提供されるサービスを利用することが必要になる場合があります。 さらに、この2番目のオブジェクトが最初の部分の自然な部分として表示されるようにします。 COM は、包含と集約によってこれらの両方の目標を達成します。

集計とは、コンテナー (外側) のオブジェクトが作成プロセスの一部として包含 (内部) オブジェクトを作成し、内側のオブジェクトのインターフェイスが外側のによって公開されることを意味します。 オブジェクトは、それ自体を集計可能にすることができます。 そのような場合は、集計が適切に機能するように、特定のルールに従っている必要があります。

主に、含まれているオブジェクトのすべての `IUnknown` メソッド呼び出しは、含んでいるオブジェクトにデリゲートする必要があります。

## <a name="see-also"></a>関連項目

[COM の概要](../atl/introduction-to-com.md)<br/>
[オブジェクトの再利用](/windows/win32/com/reusing-objects)
