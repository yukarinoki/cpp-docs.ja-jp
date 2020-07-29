---
title: コネクション ポイント
ms.date: 11/19/2018
f1_keywords:
- IConnectionPoint
helpviewer_keywords:
- IConnectionPoint interface
- connections, connection points
- OLE COM connection points
- MFC COM, connection points
- COM, connection points
- interfaces, IConnectionPoint
- MFC, COM support
- connection points [MFC]
- CCmdTarget class [MFC], and connection points
- sinks, connection points
ms.assetid: bc9fd7c7-8df6-4752-ac8c-0b177442c88d
ms.openlocfilehash: c14d8247be2abdf828b88e728bd930691ec6571f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214153"
---
# <a name="connection-points"></a>コネクション ポイント

この記事では、MFC クラスおよびを使用して、接続ポイント (旧称 OLE connection points) を実装する方法について説明し `CCmdTarget` `CConnectionPoint` ます。

以前は、コンポーネントオブジェクトモデル (COM) は、 `IUnknown::QueryInterface` オブジェクトを実装し、インターフェイスに機能を公開するために使用できる汎用機構 (*) を定義していました。 ただし、オブジェクトが特定のインターフェイスを呼び出すことができるようにするための対応する機構は定義されていません。 つまり、COM は、オブジェクトへの受信ポインター (そのオブジェクトのインターフェイスへのポインター) がどのように処理されたかを定義していましたが、送信インターフェイス (オブジェクトが他のオブジェクトのインターフェイスに保持するポインター) の明示的なモデルを持っていませんでした。 COM には、この機能をサポートする接続ポイントと呼ばれるモデルが用意されています。

接続には、ソースと呼ばれるインターフェイスを呼び出すオブジェクトと、シンクと呼ばれるインターフェイスを実装するオブジェクトの2つの部分があります。 コネクションポイントは、ソースによって公開されるインターフェイスです。 コネクションポイントを公開することにより、ソースはシンクがそれ自体への接続 (ソース) を確立できるようになります。 コネクションポイント機構 (インターフェイス) を使用して、 `IConnectionPoint` シンクインターフェイスへのポインターがソースオブジェクトに渡されます。 このポインターは、ソースに、一連のメンバー関数のシンクの実装へのアクセスを提供します。 たとえば、シンクによって実装されたイベントを発生させるには、ソースはシンクの実装の適切なメソッドを呼び出すことができます。 次の図は、ここで説明した接続ポイントを示しています。

![実装されたコネクション ポイント](../mfc/media/vc37lh1.gif "実装されたコネクション ポイント") <br/>
コネクション ポイントの実装

MFC では、 [CConnectionPoint](reference/cconnectionpoint-class.md)クラスと[CCmdTarget](reference/ccmdtarget-class.md)クラスにこのモデルが実装されています。 から派生したクラスは、 `CConnectionPoint` `IConnectionPoint` 接続ポイントを他のオブジェクトに公開するために使用されるインターフェイスを実装します。 から派生したクラス `CCmdTarget` は、インターフェイスを実装します `IConnectionPointContainer` 。これにより、オブジェクトの使用可能なすべての接続ポイントを列挙したり、特定のコネクションポイントを検索したりできます。

クラスに実装されている各接続ポイントについて、コネクションポイントを実装する接続部分を宣言する必要があります。 1つ以上のコネクションポイントを実装する場合は、クラスで1つの接続マップも宣言する必要があります。 接続マップは、ActiveX コントロールによってサポートされる接続ポイントのテーブルです。

次の例は、単純な接続マップと1つのコネクションポイントを示しています。 最初の例では、接続マップとポイントを宣言します。2番目の例では、マップとポイントを実装しています。 は `CMyClass` 、から派生したクラスである必要があることに注意してください `CCmdTarget` 。 最初の例では、コードがクラス宣言のセクションの下に挿入され **`protected`** ます。

[!code-cpp[NVC_MFCConnectionPoints#1](codesnippet/cpp/connection-points_1.h)]

**BEGIN_CONNECTION_PART**マクロと**END_CONNECTION_PART**マクロは、 `XSampleConnPt` この特定のコネクションポイントを実装する (から派生した) 埋め込みクラスを宣言し `CConnectionPoint` ます。 メンバー関数をオーバーライドする場合 `CConnectionPoint` 、または独自のメンバー関数を追加する場合は、これらの2つのマクロの間で宣言します。 たとえば、マクロは、 `CONNECTION_IID` `CConnectionPoint::GetIID` この2つのマクロの間に配置されたメンバー関数をオーバーライドします。

2番目の例では、コントロールの実装ファイル (.cpp ファイル) にコードが挿入されます。 このコードは、接続ポイントを含む接続マップを実装し `SampleConnPt` ます。

[!code-cpp[NVC_MFCConnectionPoints#2](codesnippet/cpp/connection-points_2.cpp)]

クラスに複数のコネクションポイントがある場合は、 **BEGIN_CONNECTION_MAP**と**END_CONNECTION_MAP**マクロの間に追加の**CONNECTION_PART**マクロを挿入します。

最後に、クラスのコンストラクターにの呼び出しを追加し `EnableConnections` ます。 次に例を示します。

[!code-cpp[NVC_MFCConnectionPoints#3](codesnippet/cpp/connection-points_3.cpp)]

このコードが挿入されると、 `CCmdTarget` 派生クラスはインターフェイスのコネクションポイントを公開し `ISampleSink` ます。 次の図は、この例を示しています。

![MFC を使用して実装されたコネクション ポイント](../mfc/media/vc37lh2.gif "MFC を使用して実装されたコネクション ポイント") <br/>
MFC で実装されたコネクションポイント

通常、接続ポイントは "マルチキャスト" をサポートします。これは、同じインターフェイスに接続されている複数のシンクにブロードキャストする機能です。 次のフラグメントの例では、コネクションポイントで各シンクを反復処理することで、マルチキャストを実行する方法を示します。

[!code-cpp[NVC_MFCConnectionPoints#4](codesnippet/cpp/connection-points_4.cpp)]

この例では、接続ポイントの現在の接続のセットを、の呼び出しによって取得し `SampleConnPt` `CConnectionPoint::GetConnections` ます。 次に、接続を反復処理し、 `ISampleSink::SinkFunc` アクティブなすべての接続に対してを呼び出します。

## <a name="see-also"></a>関連項目

[MFC COM](mfc-com.md)
