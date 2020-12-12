---
description: 詳細については、「COM の概要」を参照してください。
title: COM の概要
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- COM
ms.assetid: 120735d9-db71-4ad3-a730-ce576ea2354e
ms.openlocfilehash: 635bce8c1214dddfc258ae6d2d6c7e751f778e9c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147668"
---
# <a name="introduction-to-com"></a>COM の概要

COM は、ActiveX コントロールと OLE を構築するための基本的な "オブジェクトモデル" です。 COM を使用すると、オブジェクトは、その機能を他のコンポーネントに公開したり、アプリケーションをホストしたりできます。 オブジェクトがそれ自体を公開する方法と、この公開がプロセス間およびネットワーク間でどのように機能するかを定義します。 COM は、オブジェクトのライフサイクルも定義します。

COM の基本的な概念は次のとおりです。

- [インターフェイス](../atl/interfaces-atl.md) : オブジェクトがその機能を公開するために使用する機構。

- [IUnknown](../atl/iunknown.md) -他のすべてのベースとなる基本インターフェイス。 COM を介して実行される参照カウントおよびインターフェイスクエリ機構を実装します。

- [参照カウント](../atl/reference-counting.md) —オブジェクト (または、厳密にはインターフェイス) が使用されなくなったことを判断し、それ自体を削除する方法。

- [QueryInterface](../atl/queryinterface.md) -特定のインターフェイスのオブジェクトを照会するために使用されるメソッド。

- [マーシャリング](../atl/marshaling.md) : スレッド、プロセス、およびネットワーク境界を越えてオブジェクトを使用できるようにするメカニズムです。これにより、場所を独立させることができます。

- [集計](../atl/aggregation.md) —1つのオブジェクトが別のオブジェクトを使用できるようにする方法。

## <a name="see-also"></a>関連項目

[COM と ATL の概要](../atl/introduction-to-com-and-atl.md)<br/>
[コンポーネント オブジェクト モデル](/windows/win32/com/the-component-object-model)
