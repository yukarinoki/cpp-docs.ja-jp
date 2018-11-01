---
title: ATL コネクション ポイント
ms.date: 11/04/2016
helpviewer_keywords:
- connections, connection points
- ATL, connection points
- connection points [C++], about connection points
ms.assetid: 17d76165-5f83-4f95-b36d-483821c247a1
ms.openlocfilehash: 5d203d228ed2171a901f65cd01af8bd0d9703517
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511593"
---
# <a name="atl-connection-points"></a>ATL コネクション ポイント

接続可能オブジェクトは、着信インターフェイスをサポートしているオブジェクトです。 着信インターフェイスにより、オブジェクトはクライアントと通信できます。 着信インターフェイスごとに、接続可能なオブジェクトは接続ポイントを公開しています。 各着信インターフェイスは、シンクと呼ばれるオブジェクト上のクライアントによって実装されます。

![接続ポイント](../atl/media/vc2zw31.gif "vc2zw31")

各接続ポイントをサポートしています、 [IConnectionPoint](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpoint)インターフェイス。 接続可能オブジェクトを使用してクライアントに接続ポイントを公開する、 [IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)インターフェイス。

## <a name="in-this-section"></a>このセクションの内容

[ATL コネクション ポイント クラス](../atl/atl-connection-point-classes.md)<br/>
接続ポイントをサポートする ATL クラスを簡単に説明します。

[オブジェクトへの接続ポイントの追加](../atl/adding-connection-points-to-an-object.md)<br/>
オブジェクトに接続ポイントを追加するためのステップについて説明します。

[ATL コネクション ポイントの例](../atl/atl-connection-point-example.md)<br/>
接続ポイントの宣言の例を示します。

## <a name="related-sections"></a>関連項目

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Active Template Library を使用してプログラミングする方法に関する概念説明のトピックへのリンクを提供します。

## <a name="see-also"></a>関連項目

[概念](../atl/active-template-library-atl-concepts.md)

