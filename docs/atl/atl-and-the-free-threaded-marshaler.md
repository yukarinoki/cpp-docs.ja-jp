---
title: ATL とフリー スレッド マーシャラー |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, free threaded marshaler
- free threaded marshaler
- threading [C++], marshaler in ATL
- threading [ATL], free threaded marshaler
- FTM in ATL
ms.assetid: 2db88a13-2217-4ebc-aa7e-432d5da902eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 015b07e5870aa6269dc76af8610d42fb469a6d33
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848351"
---
# <a name="atl-and-the-free-threaded-marshaler"></a>ATL とフリー スレッド マーシャラー
ATL シンプル オブジェクト ウィザードの [属性] ページでは、フリー スレッド マーシャラー (FTM) を集計するのには、クラスを許可するオプションを提供します。  
  
 ウィザードでのフリー スレッド マーシャラーのインスタンスを作成するコードを生成`FinalConstruct`でそのインスタンスを解放し、`FinalRelease`します。 定義マクロは自動的にいることを確認する COM マップに追加`QueryInterface`要求[IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707)フリー スレッド マーシャラーによって処理されます。  
  
 フリー スレッド マーシャラーに直接アクセスできるオブジェクトのインターフェイス、同じプロセスで任意のスレッドからアパートメント間呼び出しの高速化します。 このオプションは、両方スレッド処理モデルを使用するクラスを対象としています。  
  
 このオプションを使用する場合、クラスは、データのスレッド セーフの責任を負う必要があります。 さらに、フリー スレッド マーシャラーを集約し、その他のオブジェクトから取得したインターフェイス ポインターを使用する必要があるオブジェクトは、インターフェイスが正しくマーシャ リングすることを確認する追加の手順を実行する必要があります。 通常これは、グローバル インターフェイス テーブル (GIT) のインターフェイス ポインターを格納して、使用されるたびに、GIT からポインターを取得する必要があります。 ATL クラスを提供します。 [CComGITPtr](../atl/reference/ccomgitptr-class.md) 、GIT に格納されているインターフェイス ポインターを使用できるようにします。  
  
## <a name="see-also"></a>関連項目  
 [概念](../atl/active-template-library-atl-concepts.md)   
 [CoCreateFreeThreadedMarshaler](http://msdn.microsoft.com/library/windows/desktop/ms694500)   
 [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707)   
 [グローバル インターフェイス テーブルを使用する場合](http://msdn.microsoft.com/library/windows/desktop/ms693729)   
 [プロセス サーバーのスレッド処理の問題](http://msdn.microsoft.com/library/windows/desktop/ms687205)

