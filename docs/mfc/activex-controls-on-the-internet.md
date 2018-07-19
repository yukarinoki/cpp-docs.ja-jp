---
title: インターネット上の ActiveX コントロール |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [MFC], creating
- ActiveX controls [MFC], Internet
- downloading data with ActiveX controls
- OLE controls [MFC], upgrading to ActiveX
- Internet applications [MFC], ActiveX controls
- networks [MFC], downloading with ActiveX controls
ms.assetid: 7ab943c8-2022-41df-9065-d629b616eeec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 02a4c2e8d9da553ffe14c8d9d061d11d7357c19c
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931978"
---
# <a name="activex-controls-on-the-internet"></a>インターネット上の ActiveX コントロール
ActiveX コントロールは、更新されたバージョンの OLE コントロールの仕様です。 コントロールは、さまざまなインターネット上の COM 対応の Web ブラウザーも含めて、別のコンテナーで使用できるプログラミング可能なソフトウェア コンポーネントを開発するための基本的なアーキテクチャです。 ActiveX コントロール インターネット制御とできます作業中の文書にその機能を追加したり、Web ページの一部にします。 Web ページ上のコントロールは、スクリプトを使用して相互に通信できます。  
  
 ActiveX コントロールは、インターネットに限定されません。 コントロールは、そのコンテナーが必要なインターフェイスをサポートしている限り、ActiveX コントロールを任意のコンテナーで使用もできます。  
  
 **ActiveX コントロールがあるなど、いくつかの利点。**  
  
-   インターフェイスは、以前の OLE コントロールよりも少ない必要です。  
  
-   ウィンドウなしであるし、常に、インプレース アクティブです。  
  
 **ActiveX コントロールをするために、コントロールが必要です。**  
  
-   サポート、`IUnknown`インターフェイスです。  
  
-   COM オブジェクトであります。  
  
-   エクスポート**DLLRegisterServer**と**DLLUnRegisterServer**です。  
  
-   機能に必要な追加のインターフェイスをサポートします。  
  
## <a name="making-your-existing-controls-internet-friendly"></a>既存のコントロールをインターネット対応にします。  
 インターネット環境で正常に機能するコントロールの設計には、インターネット上の相対的に低い伝送速度に関する考慮事項が必要です。 既存のコントロールを使用することができます。ただしは手順のコードのサイズを小さくし、コントロール プロパティを非同期的にダウンロードする必要があります。  
  
 コントロールのパフォーマンスを向上させるのには、次のヒントを参考に効率性に関する考慮事項を実行します。  
  
-   記事で説明する手法を実装する[ActiveX コントロール: 最適化](../mfc/mfc-activex-controls-optimization.md)です。  
  
-   コントロールがインスタンス化される方法を検討してください。  
  
-   非同期です。他のプログラムを保持しません。  
  
-   小さなブロック内のデータをダウンロードします。  
  
     ビットマップやビデオ データなどの大量のストリームをダウンロードするときに非同期でコンテナーを利用して、コントロールのデータにアクセスします。 データも取得するその他のコントロールで協調して、増分または連続的な方法でデータを取得します。 コードは、非同期的にもダウンロードできます。  
  
-   コードと、バック グラウンドでプロパティをダウンロードします。  
  
-   ユーザー インターフェイス、できるだけ早くとしてアクティブにします。  
  
-   検討してください (ビットマップ画像またはビデオ データ) などのプロパティと大規模なデータの両方が Blob 永続的なデータの格納方法。  
  
     大きいビットマップまたは AVI ファイルなどの永続的なデータの量が大幅にコントロールでは、ダウンロードの方法に注意が必要です。 ドキュメントまたはページは、できるだけ早く現れます、コントロールがバック グラウンドでデータを取得中に、ページと対話するユーザーを許可します。  
  
-   コードのサイズを保持し、実行時間を短くする効率的なルーチンを記述します。  
  
     だけのバイト数が、永続データと、小規模のボタンとラベル コントロールは、ブラウザー内で、作業とインターネット環境で使用するために適しています。  
  
-   進行状況は、コンテナーに伝達されることを検討してください。  
  
     など、ユーザーが、ページと対話する起動時、ダウンロードが完了すると、非同期のダウンロードの進行中のコンテナーに通知します。 コンテナーできます進行状況 (達成率など) ユーザーに表示します。  
  
-   クライアント コンピューターでコントロールを登録する方法を検討してください。  
  
## <a name="creating-a-new-activex-control"></a>新しい ActiveX コントロールの作成  
 アプリケーション ウィザードを使用して、新しいコントロールを作成するときにその他の最適化と非同期モニカーのサポートを有効にすることもできます。 コントロールのプロパティを非同期的にダウンロードするのには、サポートを追加するには、次の手順を実行します。  
  
#### <a name="to-create-your-project-using-the-mfc-activex-control-wizard"></a>MFC ActiveX コントロール ウィザードを使用して、プロジェクトを作成するには  
  
1.  をクリックして**新規**上、**ファイル**メニュー。  
  
2.  選択**MFC ActiveX コントロール ウィザード**から Visual C プロジェクトし、プロジェクトの名前します。  
  
3.  **コントロール設定**] ページで、[**プロパティを非同期的にロード**です。 このオプションを選択する準備完了の状態プロパティおよび状態変更イベントを設定します。  
  
     など、その他の最適化を選択することもできます。**ウィンドウなしのアクティベーション**、に記載されている[ActiveX コントロール: 最適化](../mfc/mfc-activex-controls-optimization.md)です。  
  
4.  選択**完了**プロジェクトを作成します。  
  
#### <a name="to-create-a-class-derived-from-cdatapathproperty"></a>関数から派生したクラスを作成するには  
  
1.  派生するクラスを作成する`CDataPathProperty`です。  
  
2.  各コントロールのヘッダー ファイルを含むソース ファイルでは、前に、このクラスのヘッダー ファイルを追加します。  
  
3.  このクラスでオーバーライド`OnDataAvailable`です。 この関数は、データを表示するために使用できるときに呼び出されます。 データが使用可能になるとは、任意の方法、たとえば徐々 にそれを表示して、処理できます。  
  
     次に示すコードでは、段階的にデータを表示するエディット コントロールでの単純な例を示します。 フラグの使用に注意してください**BSCF_FIRSTDATANOTIFICATION**エディット コントロールをオフにします。  
  
     [!code-cpp[NVC_MFCActiveXControl#1](../mfc/codesnippet/cpp/activex-controls-on-the-internet_1.cpp)]  
  
     AFXCMN を含める必要がある注意してください。使用する H、`CListCtrl`クラスです。  
  
4.  コントロールの全体的な状態が変化 (たとえば、読み込みに初期化またはユーザーから対話型)、呼び出し`COleControl::InternalSetReadyState`です。 コードを追加するには、コントロールに 1 つのデータ パスのプロパティがある場合は、**知らせる**ダウンロードが完了したコンテナーに通知します。 例えば:  
  
     [!code-cpp[NVC_MFCActiveXControl#2](../mfc/codesnippet/cpp/activex-controls-on-the-internet_2.cpp)]  
  
5.  `OnProgress` をオーバーライドします。 `OnProgress`の最大範囲を示す数値が渡されましたが、現在のダウンロードにどの程度の数を表示します。 これらの番号を使用すると、ユーザーに達成率などの状態を表示します。  
  
 次の手順では、した派生クラスを使用するコントロールにプロパティを追加します。  
  
#### <a name="to-add-a-property"></a>プロパティを追加するには  
  
1.  **クラス ビュー**ライブラリ ノードの下のインターフェイスを右クリックし、選択、**追加**、し**プロパティの追加**です。 これが開始され、**プロパティの追加ウィザード**です。  
  
2.  **プロパティの追加ウィザード**、select、 **Set/get メソッド**ラジオ ボタン、型、**プロパティ名**例、EditControlText、および、としてBSTRを選択するために、**プロパティの型**です。  
  
3.  **[完了]** をクリックします。  
  
4.  メンバー変数を宣言、 `CDataPathProperty`-ActiveX コントロール クラスにクラスを派生します。  
  
     [!code-cpp[NVC_MFCActiveXControl#3](../mfc/codesnippet/cpp/activex-controls-on-the-internet_3.h)]  
  
5.  `Get/Set` メソッドを実装します。 `Get`文字列を返します。 `Set`、プロパティと呼び出しを読み込む`SetModifiedFlag`します。  
  
     [!code-cpp[NVC_MFCActiveXControl#4](../mfc/codesnippet/cpp/activex-controls-on-the-internet_4.cpp)]  
  
6.  [DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange)、次の行を追加します。  
  
     [!code-cpp[NVC_MFCActiveXControl#5](../mfc/codesnippet/cpp/activex-controls-on-the-internet_5.cpp)]  
  
7.  オーバーライド[ResetData](../mfc/reference/cdatapathproperty-class.md#resetdata)にこの行を追加してコントロールをリセットするプロパティを通知します。  
  
     [!code-cpp[NVC_MFCActiveXControl#6](../mfc/codesnippet/cpp/activex-controls-on-the-internet_6.cpp)]  
  
## <a name="deciding-whether-to-derive-from-cdatapathproperty-or-ccacheddatapathproperty"></a>関数またはプロパティから派生するかどうかを決定します。  
 前の例から、コントロールのプロパティを派生させるための手順を説明する`CDataPathProperty`です。 これは、頻繁に変更されると、すべてのデータが、現在の値のみを保持する必要のないリアルタイムのデータをダウンロードする場合は、適切な選択です。 例では、株価表示器コントロールです。  
  
 派生できますも`CCachedDataPathProperty`します。 この例では、ダウンロードされたデータは、メモリ ファイルにキャッシュされます。 これは、ダウンロードされたすべてのデータを保持する必要がある場合の適切な選択 — 徐々 にビットマップを描画するコントロールなどです。 この例では、クラスには、データを含むメンバー変数があります。  
  
 `CMemFile m_Cache;`  
  
 ActiveX コントロール クラスで、このメモリ マップト ファイルを使用することができます`OnDraw`データを表示します。 ActiveX コントロールで`CCachedDataPathProperty`-派生クラスでは、メンバー関数をオーバーライド`OnDataAvailable`し、基本クラスの実装の呼び出し後に、コントロールを無効にします。  
  
 [!code-cpp[NVC_MFCActiveXControl#7](../mfc/codesnippet/cpp/activex-controls-on-the-internet_7.cpp)]  
  
## <a name="downloading-data-asynchronously-using-activex-controls"></a>ActiveX コントロールを使用して非同期的にデータをダウンロードします。  
 ネットワーク経由でデータのダウンロードは非同期に実行する必要があります。 これの利点は、そのためは大量のデータが転送されるか、ダウンロード プロセスでは、クライアントの他のプロセスはブロックされません、接続速度が遅い場合。  
  
 非同期モニカーでは、ネットワーク経由でデータを非同期的にダウンロードする方法を提供します。 非同期モニカーで読み取り操作は、操作が完了していない場合でも即座に返します。  
  
 たとえば、10 バイトが使用可能および読み取りが非同期的に 1 K ファイルで呼び出されると、のみ読み取りはブロックしませんで現在使用可能な 10 バイトを返します。  
  
 実装する[非同期モニカー](../mfc/asynchronous-monikers-on-the-internet.md)を使用して、`CAsyncMonikerFile`クラスです。 ただし、ActiveX コントロールを使用して、`CDataPathProperty`から派生したクラス`CAsyncMonikerFile`、非同期のコントロールのプロパティの実装に役立ちます。  
  
 ASYNDOWN サンプルでは、データの読み取りにタイマーを使用して、非同期ループを設定する方法を示します。 ASYNDOWN は"HOWTO:: AsyncDown 示します非同期のデータのダウンロード"(Q177244)、サポート技術情報の記事で詳しく説明したし、は、Microsoft ダウンロード センターからダウンロードできます。 (詳細については、Microsoft ダウンロード センターからファイルをダウンロードする、「方法に入手 Microsoft サポート オンライン サービスからファイル」(Q119591) では、Microsoft サポート技術情報の記事を参照してください)。サポート技術情報を見つけることができます[ http://support.microsoft.com/support](http://support.microsoft.com/support)です。  
  
 ASYNDOWN で使用される基本的な手法タイマーを設定する**CDataPathProperty::OnDataAvailable**データが使用可能なことを示すです。 タイマー メッセージを受信すると、アプリケーションが 128 バイトのデータ ブロックの読み取りし、エディット コントロールします。 タイマー メッセージを処理するときにデータが使用できない場合は、タイマーはになっています。 `OnDataAvailable` 多くのデータを後で受信した場合に、タイマーをオンにします。  
  
## <a name="displaying-a-control-on-a-web-page"></a>Web ページ上のコントロールを表示します。  
 オブジェクト タグと Web ページ上のコントロールを挿入するための属性の使用例を次に示します。  
  
 `<OBJECT`  
  
 `CLASSID="clsid:FC25B780-75BE-11CF-8B01-444553540000"`  
  
 `CODEBASE="/ie/download/activex/iechart.ocx"`  
  
 `ID=chart1`  
  
 `WIDTH=400`  
  
 `HEIGHT=200`  
  
 `ALIGN=center`  
  
 `HSPACE=0`  
  
 `VSPACE=0`  
  
 `>`  
  
 `<PARAM NAME="BackColor" value="#ffffff">`  
  
 `<PARAM NAME="ForeColor" value="#0000ff">`  
  
 `<PARAM NAME="url" VALUE="/ie/controls/chart/mychart.txt">`  
  
 `</OBJECT>`  
  
## <a name="updating-an-existing-ole-control-to-use-new-activex-control-features"></a>ActiveX コントロールの新機能を使用する既存の OLE コントロールの更新  
 OLE コントロールは、Visual C の 4.2 より前のバージョンで作成されている場合は、そのパフォーマンスが向上し、その機能を強化するために行える手順があります。 これらの変更の詳細については、次を参照してください。 [ActiveX コントロール: 最適化](../mfc/mfc-activex-controls-optimization.md)です。  
  
 既存のコントロールに非同期のプロパティのサポートを追加する準備完了の状態プロパティを追加する必要があります、`ReadyStateChange`イベント自分でします。 コントロールのコンス トラクターは、次のように追加します。  
  
 [!code-cpp[NVC_MFCActiveXControl#8](../mfc/codesnippet/cpp/activex-controls-on-the-internet_8.cpp)]  
  
 呼び出すことによって、コードがダウンロードしたとして準備完了状態を更新[中](../mfc/reference/colecontrol-class.md#internalsetreadystate)です。 呼び出すことが 1 か所`InternalSetReadyState`からは、`OnProgress`のオーバーライド`CDataPathProperty`-クラスを派生します。  
  

  
## <a name="see-also"></a>関連項目  
 [MFC インターネット プログラミングの作業](../mfc/mfc-internet-programming-tasks.md)   
 [MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)

