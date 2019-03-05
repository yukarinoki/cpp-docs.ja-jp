---
title: ATL とフリー スレッド マーシャラー
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, free threaded marshaler
- free threaded marshaler
- threading [C++], marshaler in ATL
- threading [ATL], free threaded marshaler
- FTM in ATL
ms.assetid: 2db88a13-2217-4ebc-aa7e-432d5da902eb
ms.openlocfilehash: ddea5a74dbd40d097398d04c0b2bc274df5ec972
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299999"
---
# <a name="atl-and-the-free-threaded-marshaler"></a>ATL とフリー スレッド マーシャラー

ATL シンプル オブジェクト ウィザードの [属性] ページでは、フリー スレッド マーシャラー (FTM) を集計するのには、クラスを許可するオプションを提供します。

ウィザードでのフリー スレッド マーシャラーのインスタンスを作成するコードを生成`FinalConstruct`でそのインスタンスを解放し、`FinalRelease`します。 定義マクロは自動的にいることを確認する COM マップに追加`QueryInterface`要求[IMarshal](/windows/desktop/api/objidlbase/nn-objidlbase-imarshal)フリー スレッド マーシャラーによって処理されます。

フリー スレッド マーシャラーに直接アクセスできるオブジェクトのインターフェイス、同じプロセスで任意のスレッドからアパートメント間呼び出しの高速化します。 このオプションは、両方スレッド処理モデルを使用するクラスを対象としています。

このオプションを使用する場合、クラスは、データのスレッド セーフの責任を負う必要があります。 さらに、フリー スレッド マーシャラーを集約し、その他のオブジェクトから取得したインターフェイス ポインターを使用する必要があるオブジェクトは、インターフェイスが正しくマーシャ リングすることを確認する追加の手順を実行する必要があります。 通常これは、グローバル インターフェイス テーブル (GIT) のインターフェイス ポインターを格納して、使用されるたびに、GIT からポインターを取得する必要があります。 ATL クラスを提供します。 [CComGITPtr](../atl/reference/ccomgitptr-class.md) 、GIT に格納されているインターフェイス ポインターを使用できるようにします。

## <a name="see-also"></a>関連項目

[概念](../atl/active-template-library-atl-concepts.md)<br/>
[CoCreateFreeThreadedMarshaler](/windows/desktop/api/combaseapi/nf-combaseapi-cocreatefreethreadedmarshaler)<br/>
[IMarshal](/windows/desktop/api/objidlbase/nn-objidlbase-imarshal)<br/>
[グローバル インターフェイス テーブルを使用する場合](/windows/desktop/com/when-to-use-the-global-interface-table)<br/>
[プロセス サーバーのスレッド処理の問題](/windows/desktop/com/in-process-server-threading-issues)
