---
title: プロバイダー サービスの既定のオーバーライド
ms.date: 10/29/2018
helpviewer_keywords:
- service providers [OLE DB]
- OLE DB services [OLE DB], overriding defaults
ms.assetid: 08e366c0-74d8-463b-93a6-d58a8dc195f8
ms.openlocfilehash: 9f845834b844c16bf2820a295768696e8f6a6526
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556297"
---
# <a name="overriding-provider-service-defaults"></a>プロバイダー サービスの既定のオーバーライド

既定値として OLEDB_SERVICES のプロバイダーのレジストリ値が返されます、 [DBPROP_INIT_OLEDBSERVICES](https://docs.microsoft.com/previous-versions/windows/desktop/ms716898(v=vs.85))データ ソース オブジェクトのプロパティを初期化します。

レジストリ エントリが存在する限り、プロバイダーのオブジェクトが集計されます。 ユーザーは、プロバイダーの既定の初期化の前にされますが有効なサービス設定をオーバーライドできます。 有効にまたは特定のサービスを無効にするには、ユーザー DBPROP_INIT_OLEDBSERVICES プロパティの現在の値を取得、設定またはのビットを有効または無効になっている、特定のプロパティをクリアしますおよびプロパティをリセットします。 OLE DB または ADO に渡される接続文字列で直接、DBPROP_INIT_OLEDBSERVICES を設定できますか`IDataInitialize::GetDatasource`します。 個々 のサービスを有効または無効にする、対応する値は、次の表に表示されます。

|既定のサービスを有効になっています。|DBPROP_INIT_OLEDBSERVICES プロパティの値|接続文字列を値します。|
|------------------------------|------------------------------------------------|--------------------------------|
|すべてのサービス (既定値)|DBPROPVAL_OS_ENABLEALL|"OLE DB サービス =-1;"|
|プールを除くすべてと自動確保|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_RESOURCEPOOLING &`<br /><br /> `~DBPROPVAL_OS_TXNENLISTMENT`|"OLE DB サービス =-4;"|
|クライアント カーソルを除くすべて|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_CLIENTCURSOR`|"OLE DB サービス =-5;"|
|プールで自動確保、およびクライアント カーソルを除くすべて|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_TXNENLISTMENT &`<br /><br /> `~DBPROPVAL_OS_CLIENTCURSOR`|"OLE DB サービス =-7;"|
|サービスはありません。|`~DBPROPVAL_OS_ENABLEALL`|"OLE DB サービス = 0;"|

プロバイダーのレジストリ エントリが存在しない場合、コンポーネント マネージャーはプロバイダーのオブジェクトを収集しません。 サービスはオンなしになります、場合でも、ユーザーによって明示的に要求します。

## <a name="see-also"></a>関連項目

[リソース プール](https://docs.microsoft.com/previous-versions/windows/desktop/ms713655(v=vs.85))<br/>
[コンシューマーがリソース プールを使用する方法](https://docs.microsoft.com/previous-versions/windows/desktop/ms715907(v=vs.85))<br/>
[プロバイダーとの連携効果的にリソース プール](https://docs.microsoft.com/previous-versions/windows/desktop/ms714906(v=vs.85))<br/>
[OLE DB サービスの有効化と無効化](../../data/oledb/enabling-and-disabling-ole-db-services.md)<br/>