---
description: '詳細情報: プロバイダーサービスの既定値のオーバーライド'
title: プロバイダー サービスの既定のオーバーライド
ms.date: 10/29/2018
helpviewer_keywords:
- service providers [OLE DB]
- OLE DB services [OLE DB], overriding defaults
ms.assetid: 08e366c0-74d8-463b-93a6-d58a8dc195f8
ms.openlocfilehash: eca6045c347ee8dc9295540d17bfc8feb225a73b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316922"
---
# <a name="overriding-provider-service-defaults"></a>プロバイダー サービスの既定のオーバーライド

OLEDB_SERVICES のプロバイダーのレジストリ値は、データソースオブジェクトの [DBPROP_INIT_OLEDBSERVICES](/previous-versions/windows/desktop/ms716898(v=vs.85)) 初期化プロパティの既定値として返されます。

レジストリエントリが存在する限り、プロバイダーのオブジェクトが集計されます。 ユーザーは、初期化の前に DBPROP_INIT_OLEDBSERVICES プロパティを設定することによって、有効になっているサービスに対するプロバイダーの既定の設定をオーバーライドできます。 特定のサービスを有効または無効にするには、ユーザーは DBPROP_INIT_OLEDBSERVICES プロパティの現在の値を取得し、有効または無効にする特定のプロパティのビットを設定またはクリアして、プロパティをリセットします。 DBPROP_INIT_OLEDBSERVICES は、OLE DB または ADO またはに渡される接続文字列で直接設定でき `IDataInitialize::GetDatasource` ます。 次の表に、個々のサービスを有効または無効にするための対応する値を示します。

|既定のサービスが有効|DBPROP_INIT_OLEDBSERVICES プロパティ値|接続文字列の値|
|------------------------------|------------------------------------------------|--------------------------------|
|すべてのサービス (既定)|DBPROPVAL_OS_ENABLEALL|"OLE DB Services =-1;"|
|プーリングと AutoEnlistment を除くすべて|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_RESOURCEPOOLING &`<br /><br /> `~DBPROPVAL_OS_TXNENLISTMENT`|"OLE DB Services =-4;"|
|クライアントカーソル以外のすべて|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_CLIENTCURSOR`|"OLE DB Services =-5;"|
|プール、AutoEnlistment、およびクライアントカーソル以外のすべて|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_TXNENLISTMENT &`<br /><br /> `~DBPROPVAL_OS_CLIENTCURSOR`|"OLE DB Services =-7;"|
|サービスがありません|`~DBPROPVAL_OS_ENABLEALL`|"OLE DB Services = 0;"|

プロバイダーのレジストリエントリが存在しない場合、コンポーネントマネージャーはプロバイダーのオブジェクトを収集しません。 ユーザーによって明示的に要求された場合でも、サービスは有効になりません。

## <a name="see-also"></a>関連項目

[リソースプーリング](/previous-versions/windows/desktop/ms713655(v=vs.85))<br/>
[コンシューマーがリソースプールを使用する方法](/previous-versions/windows/desktop/ms715907(v=vs.85))<br/>
[リソースプーリングを使用してプロバイダーを効果的に動作させる方法](/previous-versions/windows/desktop/ms714906(v=vs.85))<br/>
[OLE DB サービスの有効化と無効化](../../data/oledb/enabling-and-disabling-ole-db-services.md)<br/>
