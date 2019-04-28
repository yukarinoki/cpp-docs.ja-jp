---
title: ATL コネクション ポイント
ms.date: 11/04/2016
helpviewer_keywords:
- connections, connection points
- ATL, connection points
- connection points [C++], about connection points
ms.assetid: 17d76165-5f83-4f95-b36d-483821c247a1
ms.openlocfilehash: 4d94396ef8839516d9bfee15a2611cce66baa6bd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252318"
---
# <a name="atl-connection-points"></a>ATL コネクション ポイント

接続可能オブジェクトは、着信インターフェイスをサポートしているオブジェクトです。 着信インターフェイスにより、オブジェクトはクライアントと通信できます。 着信インターフェイスごとに、接続可能なオブジェクトは接続ポイントを公開しています。 各着信インターフェイスは、シンクと呼ばれるオブジェクト上のクライアントによって実装されます。

![接続ポイント](../atl/media/vc2zw31.gif "コネクション ポイント")

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
