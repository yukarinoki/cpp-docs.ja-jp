---
title: COM の概要
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- COM
ms.assetid: 120735d9-db71-4ad3-a730-ce576ea2354e
ms.openlocfilehash: 7a200a964e0cba09878929e4362385e5badd10c1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492858"
---
# <a name="introduction-to-com"></a>COM の概要

COM は、どの ActiveX コントロールと OLE のビルドで、基本的な「オブジェクト モデル」。 COM は、他のコンポーネントやアプリケーションをホストする機能を公開するオブジェクトを許可します。 オブジェクトがそれ自体を公開する方法と、プロセス間で、ネットワーク間でのこの公開の動作を定義します。 COM には、オブジェクトのライフ サイクルも定義します。

COM の基盤は、これらの概念です。

- [インターフェイス](../atl/interfaces-atl.md)— オブジェクトを使用するには、機能を公開するメカニズムです。

- [IUnknown](../atl/iunknown.md) -他のすべてのユーザーは基になる基本インターフェイスです。 参照カウントや COM 経由で実行されているメカニズムのクエリを実行するインターフェイスを実装します。

- [参照カウント](../atl/reference-counting.md)— されるオブジェクト (または、厳密には、インターフェイス) と、使用しなくなったと決定自体を削除する無料ではそのための手法です。

- [QueryInterface](../atl/queryinterface.md) -特定のインターフェイスのオブジェクトのクエリに使用する方法。

- [マーシャ リング](../atl/marshaling.md): スレッド、プロセス、および場所に依存しないのため、ネットワーク境界全体で使用するオブジェクトを使用するメカニズムです。

- [集計](../atl/aggregation.md)-別の 1 つのオブジェクトの作成に使用できる方法を使用します。

## <a name="see-also"></a>関連項目

[COM と ATL の概要](../atl/introduction-to-com-and-atl.md)<br/>
[コンポーネント オブジェクト モデル](/windows/desktop/com/the-component-object-model)

