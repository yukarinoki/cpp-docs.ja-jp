---
title: インターネット上の非同期モニカー
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX controls [MFC], asynchronous
- MFC, asynchronous monikers
- asynchronous monikers [MFC]
- Web applications [MFC], asynchronous
- downloading Internet resources and asynchronous monikers
- optimization [MFC], asynchronous downloading across Internet
- Internet [MFC], asynchronous downloading
ms.assetid: 418b0c64-0046-4dae-8118-c9c762b5822e
ms.openlocfilehash: 74add1ad894f883c67eefab888898c0abf518b83
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625035"
---
# <a name="asynchronous-monikers-on-the-internet"></a>インターネット上の非同期モニカー

インターネットでは、ネットワークアクセスが低速であるため、アプリケーションの設計に新しいアプローチが必要です。 アプリケーションでは、ユーザーインターフェイスの停止を避けるために、ネットワークアクセスを非同期的に実行する必要があります。 MFC クラス[CAsyncMonikerFile](reference/casyncmonikerfile-class.md)は、ファイルをダウンロードするための非同期サポートを提供します。

非同期モニカーを使用すると、COM アプリケーションを拡張して、インターネットを介して非同期的にダウンロードしたり、ビットマップや VRML オブジェクトなどのラージオブジェクトのプログレッシブレンダリングを行ったりすることができます。 非同期モニカーを使用すると、ユーザーインターフェイスの応答をブロックせずに、ActiveX コントロールプロパティまたはインターネット上のファイルをダウンロードできます。

## <a name="advantages-of-asynchronous-monikers"></a>非同期モニカーの利点

非同期モニカーを使用すると、次のことができます。

- ブロックせずにコードとファイルをダウンロードします。

- ActiveX コントロールのプロパティをブロックせずにダウンロードします。

- ダウンロードの進行状況の通知を受信します。

- 進行状況と準備完了の状態の情報を追跡します。

- 進行状況に関するステータス情報をユーザーに提供します。

- ユーザーがいつでもダウンロードをキャンセルできるようにします。

## <a name="mfc-classes-for-asynchronous-monikers"></a>非同期モニカーの MFC クラス

[CAsyncMonikerFile](reference/casyncmonikerfile-class.md)は[CMonikerFile](reference/cmonikerfile-class.md)から派生し、さらに[COleStreamFile](reference/colestreamfile-class.md)から派生します。 `COleStreamFile`オブジェクトはデータのストリームを表し、オブジェクトはを使用して `CMonikerFile` `IMoniker` データを取得し `CAsyncMonikerFile` ます。オブジェクトは非同期に行われます。

非同期モニカーは、ファイル転送中に応答性の高いユーザーインターフェイスを提供するために、主にインターネット対応アプリケーションおよび ActiveX コントロールで使用されます。 この例では、 [CDataPathProperty](reference/cdatapathproperty-class.md)を使用して、ActiveX コントロールの非同期プロパティを提供しています。

## <a name="mfc-classes-for-data-paths-in-activex-controls"></a>ActiveX コントロールのデータパスの MFC クラス

MFC クラス `CDataPathProperty` と[CCachedDataPathProperty](reference/ccacheddatapathproperty-class.md)は、非同期的に読み込むことができる ActiveX コントロールプロパティを実装します。 非同期プロパティは、同期の開始後に読み込まれます。 非同期 ActiveX コントロールは、長いプロパティ交換プロセス中に新しいデータが使用可能であることを示すために、コールバックを繰り返し呼び出します。

`CDataPathProperty` は、`CAsyncMonikerFile` から派生しています。 `CCachedDataPathProperty` は、`CDataPathProperty` から派生しています。 ActiveX コントロールに非同期プロパティを実装するには、またはからクラスを派生させ、 `CDataPathProperty` `CCachedDataPathProperty` 受信する[OnDataAvailable](reference/casyncmonikerfile-class.md#ondataavailable)とその他の通知をオーバーライドします。

#### <a name="to-download-a-file-using-asynchronous-monikers"></a>非同期モニカーを使用してファイルをダウンロードするには

1. [CAsyncMonikerFile](reference/casyncmonikerfile-class.md)から派生したクラスを宣言します。

1. [OnDataAvailable](reference/casyncmonikerfile-class.md#ondataavailable)をオーバーライドしてデータを表示します。

1. [Onprogress](reference/casyncmonikerfile-class.md#onprogress)、 [Onstartbinding](reference/casyncmonikerfile-class.md#onstartbinding)、 [onstopbinding](reference/casyncmonikerfile-class.md#onstopbinding)など、他のメンバー関数をオーバーライドします。

1. このクラスのインスタンスを宣言し、それを使用して Url を開きます。

ActiveX コントロールでの非同期ダウンロードの詳細については、「[インターネット上の Activex コントロール](activex-controls-on-the-internet.md)」を参照してください。

## <a name="see-also"></a>関連項目

[MFC インターネット プログラミングの作業](mfc-internet-programming-tasks.md)<br/>
[MFC インターネットプログラミングの基礎](mfc-internet-programming-basics.md)
