---
title: インターネット上の非同期モニカー |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [MFC], asynchronous
- MFC, asynchronous monikers
- asynchronous monikers [MFC]
- Web applications [MFC], asynchronous
- downloading Internet resources and asynchronous monikers
- optimization [MFC], asynchronous downloading across Internet
- Internet [MFC], asynchronous downloading
ms.assetid: 418b0c64-0046-4dae-8118-c9c762b5822e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fb9828734985c25996e7e2d1a6f390a0b629d998
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="asynchronous-monikers-on-the-internet"></a>インターネット上の非同期モニカー
インターネットには、低速のネットワーク アクセスのためアプリケーション デザインに新しいアプローチが必要です。 アプリケーションでは、ユーザー インターフェイスを失速を避けるために非同期的にネットワーク アクセスを実行する必要があります。 MFC クラス[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)ファイルをダウンロードする非同期サポートを提供します。  
  
 非同期モニカーを使用するには、インターネット経由で非同期的にダウンロードし、ビットマップなどのラージ オブジェクトおよび VRML オブジェクトのプログレッシブのレンダリングを提供する COM アプリケーションを拡張できます。 非同期モニカーには、ActiveX コントロールのプロパティまたはユーザー インターフェイスの応答をブロックすることがなくダウンロードするインターネット上のファイルが有効にします。  
  
## <a name="advantages-of-asynchronous-monikers"></a>非同期モニカーの利点  
 非同期モニカーを使用することができます。  
  
-   ブロックすることがなく、コードとファイルをダウンロードします。  
  
-   ブロックすることがなく、ActiveX コントロールのプロパティをダウンロードします。  
  
-   ダウンロードの進行状況の通知を受信します。  
  
-   進行状況の追跡と準備完了の状態情報。  
  
-   進行状況に関するユーザーの状態情報を提供します。  
  
-   いつでもダウンロードをキャンセルできます。  
  
## <a name="mfc-classes-for-asynchronous-monikers"></a>非同期モニカー用の MFC クラス  
 [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)から派生した[CMonikerFile](../mfc/reference/cmonikerfile-class.md)からさらに派生した[関数](../mfc/reference/colestreamfile-class.md)です。 A`COleStreamFile`データのストリーム以外の場合は、オブジェクトを表します`CMonikerFile`オブジェクトが使用、 `IMoniker` 、データを取得して、`CAsyncMonikerFile`オブジェクトは非同期的にします。  
  
 非同期モニカーは、ファイル転送中に、応答性の高いユーザー インターフェイスを提供するインターネット対応のアプリケーションと ActiveX コントロールで、主に使用されます。 この主要な例は、の使用[関数](../mfc/reference/cdatapathproperty-class.md)ActiveX コントロールの非同期プロパティを指定します。  
  
## <a name="mfc-classes-for-data-paths-in-activex-controls"></a>ActiveX コントロールにおけるデータのパス用の MFC クラス  
 MFC クラス`CDataPathProperty`と[プロパティ](../mfc/reference/ccacheddatapathproperty-class.md)非同期的に読み込むことができる ActiveX コントロールのプロパティを実装します。 同期の開始後は、非同期のプロパティが読み込まれます。 非同期の ActiveX コントロールは、時間のかかるプロパティ exchange プロセス中に新しいデータの可用性を示すためにコールバックを繰り返し呼び出します。  
  
 `CDataPathProperty` は、`CAsyncMonikerFile` から派生しています。 `CCachedDataPathProperty` は、`CDataPathProperty` から派生しています。 ActiveX コントロールでの非同期プロパティを実装するには、派生クラスを`CDataPathProperty`または`CCachedDataPathProperty`、オーバーライドと[OnDataAvailable](../mfc/reference/casyncmonikerfile-class.md#ondataavailable)およびその他の通知の受信を希望します。  
  
#### <a name="to-download-a-file-using-asynchronous-monikers"></a>非同期モニカーを使用してファイルをダウンロードするには  
  
1.  派生するクラスを宣言[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)です。  
  
2.  オーバーライド[OnDataAvailable](../mfc/reference/casyncmonikerfile-class.md#ondataavailable)データを表示します。  
  
3.  など、他のメンバー関数をオーバーライド[OnProgress](../mfc/reference/casyncmonikerfile-class.md#onprogress)、 [OnStartBinding](../mfc/reference/casyncmonikerfile-class.md#onstartbinding)、および[は](../mfc/reference/casyncmonikerfile-class.md#onstopbinding)します。  
  
4.  このクラスのインスタンスを宣言し、Url を開くために使用します。  
  
 ActiveX コントロールにおける非同期的にダウンロードについては、次を参照してください。 [、インターネット上の ActiveX コントロール](../mfc/activex-controls-on-the-internet.md)です。  
  
## <a name="see-also"></a>関連項目  
 [MFC インターネット プログラミングの作業](../mfc/mfc-internet-programming-tasks.md)   
 [MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)

