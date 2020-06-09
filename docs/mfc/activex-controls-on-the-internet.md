---
title: インターネット上の ActiveX コントロール
ms.date: 09/12/2018
helpviewer_keywords:
- ActiveX controls [MFC], creating
- ActiveX controls [MFC], Internet
- downloading data with ActiveX controls
- OLE controls [MFC], upgrading to ActiveX
- Internet applications [MFC], ActiveX controls
- networks [MFC], downloading with ActiveX controls
ms.assetid: 7ab943c8-2022-41df-9065-d629b616eeec
ms.openlocfilehash: f06a6f6f71e922163fd95c59836c50b88b05ed3a
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616475"
---
# <a name="activex-controls-on-the-internet"></a>インターネット上の ActiveX コントロール

ActiveX コントロールは、OLE コントロール仕様の更新されたバージョンです。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 詳細については、「 [ActiveX コントロール](activex-controls.md)」を参照してください。

コントロールは、インターネット上の COM 対応 Web ブラウザーを含むさまざまなコンテナーで使用できる、プログラミング可能なソフトウェアコンポーネントを開発するための主要なアーキテクチャです。 ActiveX コントロールは、インターネットコントロールにすることができます。また、アクティブなドキュメントに機能を追加したり、Web ページの一部にすることができます。 Web ページ上のコントロールは、スクリプトを使用して相互に通信できます。

ActiveX コントロールは、インターネットに限定されていません。 ActiveX コントロールは、そのコンテナーで必要なインターフェイスをサポートしていれば、任意のコンテナーで使用することもできます。

**ActiveX コントロールには、次のようないくつかの利点があります。**

- 以前の OLE コントロールよりも必要なインターフェイスが減ります。

- ウィンドウなしで、常にアクティブにする機能。

**ActiveX コントロールにするために、コントロールは次の操作を行う必要があります。**

- インターフェイスをサポート `IUnknown` します。

- COM オブジェクトである。

- **DLLRegisterServer**と**DLLUnRegisterServer**をエクスポートします。

- 機能に必要な追加のインターフェイスをサポートします。

## <a name="making-your-existing-controls-internet-friendly"></a>既存のコントロールをインターネットで使いやすくする

インターネット環境で適切に機能するコントロールを設計するには、インターネット上で比較的低転送速度を考慮する必要があります。 既存のコントロールを使用できます。ただし、コードサイズを小さくし、コントロールプロパティを非同期にダウンロードするために実行する必要がある手順があります。

コントロールのパフォーマンスを向上させるには、効率性に関する考慮事項に関する次のヒントに従ってください。

- 「 [ActiveX コントロール: 最適化](mfc-activex-controls-optimization.md)」で説明されている手法を実装します。

- コントロールがインスタンス化される方法を検討します。

- 非同期である。他のプログラムを保持しないでください。

- 小さいブロックでデータをダウンロードします。

   ビットマップやビデオデータなどの大規模なストリームをダウンロードする場合は、コンテナーと連携して、コントロールのデータに非同期にアクセスします。 データを増分またはプログレッシブ方式で取得し、データを取得する可能性がある他のコントロールと協調して作業します。 コードを非同期的にダウンロードすることもできます。

- コードとプロパティをバックグラウンドでダウンロードします。

- ユーザーインターフェイスをできるだけ早くアクティブにします。

- 永続データの格納方法、プロパティと大きなデータ Blob (ビットマップイメージ、ビデオデータなど) を考慮してください。

   大きなビットマップや AVI ファイルなど、大量の永続データを持つコントロールでは、メソッドのダウンロードに注意する必要があります。 ドキュメントまたはページは、できるだけ早く表示される可能性があります。また、コントロールがバックグラウンドでデータを取得するときに、ユーザーがページと対話できるようになります。

- コードサイズと実行時間を維持するための効率的なルーチンを記述します。

   わずか数バイトの永続データを持つ小さいボタンとラベルのコントロールは、インターネット環境での使用に適しており、ブラウザー内で適切に動作します。

- 進行状況をコンテナーに伝達することを検討します。

   ユーザーがページとの対話を開始できるタイミングやダウンロードが完了したときなど、非同期ダウンロードで進行状況をコンテナーに通知します。 コンテナーでは、ユーザーに進行状況 (パーセント完了など) を表示できます。

- クライアントコンピューターでのコントロールの登録方法を検討します。

## <a name="creating-a-new-activex-control"></a>新しい ActiveX コントロールの作成

アプリケーションウィザードを使用して新しいコントロールを作成する場合、非同期モニカーとその他の最適化のサポートを有効にすることもできます。 コントロールのプロパティを非同期的にダウンロードするためのサポートを追加するには、次の手順を実行します。

#### <a name="to-create-your-project-using-the-mfc-activex-control-wizard"></a>MFC ActiveX コントロールウィザードを使用してプロジェクトを作成するには

1. [**ファイル**] メニューの [**新規作成**] をクリックします。

1. Visual Studio C++ プロジェクトの [ **MFC ActiveX コントロールウィザード**] を選択し、プロジェクトの名前を指定します。

1. [**コントロールの設定**] ページで、[プロパティを**非同期に読み込む**] を選択します。 このオプションを選択すると、準備完了状態プロパティと準備完了状態変更イベントが設定されます。

   **ウィンドウなしのアクティブ化**など、他の最適化を選択することもできます。これについては、「 [ActiveX コントロール: 最適化](mfc-activex-controls-optimization.md)」を参照してください。

1. **[完了]** を選択して、プロジェクトを作成します。

#### <a name="to-create-a-class-derived-from-cdatapathproperty"></a>CDataPathProperty から派生したクラスを作成するには

1. から派生したクラスを作成 `CDataPathProperty` します。

1. 各ソースファイルには、コントロールのヘッダーファイルが含まれています。その前に、このクラスのヘッダーファイルを追加します。

1. このクラスでは、をオーバーライド `OnDataAvailable` します。 この関数は、データを表示できるようにするたびに呼び出されます。 データが使用可能になると、選択した任意の方法で処理できます。たとえば、プログレッシブレンダリングを行うことができます。

   次のコード抜粋は、エディットコントロールにデータをプログレッシブ表示する簡単な例です。 **BSCF_FIRSTDATANOTIFICATION**フラグを使用して、エディットコントロールをクリアします。

   [!code-cpp[NVC_MFCActiveXControl#1](codesnippet/cpp/activex-controls-on-the-internet_1.cpp)]

   AFXCMN.H を含める必要があることに注意してください。H クラスを使用し `CListCtrl` ます。

1. コントロールの全体的な状態が変化した場合 (たとえば、読み込みから初期化済みまたはユーザー対話形式に変更した場合) は、を呼び出し `COleControl::InternalSetReadyState` ます。 コントロールにデータパスプロパティが1つしかない場合は、ダウンロードが完了したことをコンテナーに通知するコードを**BSCF_LASTDATANOTIFICATION**に追加できます。 次に例を示します。

   [!code-cpp[NVC_MFCActiveXControl#2](codesnippet/cpp/activex-controls-on-the-internet_2.cpp)]

1. `OnProgress` をオーバーライドします。 では `OnProgress` 、最大範囲と現在のダウンロードにおける距離を示す数値が渡されます。 これらの数値を使用して、ユーザーに対する完了率などの状態を表示できます。

次の手順では、プロパティをコントロールに追加して、派生したクラスを使用します。

#### <a name="to-add-a-property"></a>プロパティを追加するには

1. **クラスビュー**で、[ライブラリ] ノードの下のインターフェイスを右クリックし、[**追加**]、[**プロパティの追加**] の順に選択します。 これにより、**プロパティの追加ウィザード**が開始されます。

1. プロパティの**追加ウィザード**で、[**メソッドの設定/取得**] オプションボタンを選択し、**プロパティ名**(たとえば、Editcontroltext) を入力し、**プロパティの型**として [BSTR] を選択します。

1. **[完了]** をクリックします。

1. 派生クラスのメンバー変数を `CDataPathProperty` ActiveX コントロールクラスに宣言します。

   [!code-cpp[NVC_MFCActiveXControl#3](codesnippet/cpp/activex-controls-on-the-internet_3.h)]

1. `Get/Set` メソッドを実装します。 の `Get` 場合は、文字列を返します。 の場合は `Set` 、プロパティを読み込んでを呼び出し `SetModifiedFlag` ます。

   [!code-cpp[NVC_MFCActiveXControl#4](codesnippet/cpp/activex-controls-on-the-internet_4.cpp)]

1. [DoPropExchange](reference/colecontrol-class.md#dopropexchange)で、次の行を追加します。

   [!code-cpp[NVC_MFCActiveXControl#5](codesnippet/cpp/activex-controls-on-the-internet_5.cpp)]

1. [Resetdata](reference/cdatapathproperty-class.md#resetdata)をオーバーライドして、次の行を追加してコントロールをリセットするようにプロパティに通知します。

   [!code-cpp[NVC_MFCActiveXControl#6](codesnippet/cpp/activex-controls-on-the-internet_6.cpp)]

## <a name="deciding-whether-to-derive-from-cdatapathproperty-or-ccacheddatapathproperty"></a>CDataPathProperty または CCachedDataPathProperty から派生するかどうかを決定する

前の例では、からコントロールのプロパティを派生させる手順について説明し `CDataPathProperty` ます。 これは、頻繁に変更されるリアルタイムデータをダウンロードする場合に、すべてのデータを保持する必要がなく、現在の値のみを保持する必要がある場合に適しています。 例として、株式ティッカーコントロールなどがあります。

から派生することもでき `CCachedDataPathProperty` ます。 この場合、ダウンロードしたデータはメモリファイルにキャッシュされます。 これは、すべてのダウンロードされたデータを保持する必要がある場合に適しています。たとえば、ビットマップをプログレッシブにレンダリングするコントロールなどです。 この場合、クラスには、データを含むメンバー変数があります。

`CMemFile m_Cache;`

ActiveX コントロールクラスでは、このメモリマップファイルを使用し `OnDraw` てデータを表示できます。 ActiveX コントロールの `CCachedDataPathProperty` 派生クラスで、 `OnDataAvailable` 基底クラスの実装を呼び出した後、メンバー関数をオーバーライドし、コントロールを無効にします。

[!code-cpp[NVC_MFCActiveXControl#7](codesnippet/cpp/activex-controls-on-the-internet_7.cpp)]

## <a name="downloading-data-asynchronously-using-activex-controls"></a>ActiveX コントロールを使用してデータを非同期的にダウンロードする

ネットワーク経由でのデータのダウンロードは、非同期に実行する必要があります。 これを行う利点は、大量のデータが転送される場合や、接続速度が遅い場合、ダウンロードプロセスによってクライアント上の他のプロセスがブロックされないことです。

非同期モニカーは、ネットワーク経由でデータを非同期的にダウンロードする方法を提供します。 非同期モニカーに対する読み取り操作は、操作が完了していない場合でも直ちに返されます。

たとえば、使用できるのが10バイトだけで、読み取りが1K ファイルで非同期に呼び出される場合、Read はブロックしませんが、は現在使用可能な10バイトでを返します。

[非同期モニカー](asynchronous-monikers-on-the-internet.md)は、クラスを使用して実装し `CAsyncMonikerFile` ます。 ただし、ActiveX コントロールでは、から派生したクラスを使用して、 `CDataPathProperty` `CAsyncMonikerFile` 非同期コントロールプロパティを実装できます。

## <a name="displaying-a-control-on-a-web-page"></a>Web ページにコントロールを表示する

Web ページにコントロールを挿入するためのオブジェクトタグと属性の例を次に示します。

```xml
<OBJECT
  CLASSID="clsid:FC25B780-75BE-11CF-8B01-444553540000"
  CODEBASE="/ie/download/activex/iechart.ocx"
  ID=chart1
  WIDTH=400
  HEIGHT=200
  ALIGN=center
  HSPACE=0
  VSPACE=0>
  <PARAM NAME="BackColor" value="#ffffff"/>
  <PARAM NAME="ForeColor" value="#0000ff"/>
  <PARAM NAME="url" VALUE="/ie/controls/chart/mychart.txt"/>
</OBJECT>
```

## <a name="updating-an-existing-ole-control-to-use-new-activex-control-features"></a>新しい ActiveX コントロール機能を使用するための既存の OLE コントロールの更新

4.2 より前のバージョンの Visual C++ で OLE コントロールを作成した場合は、パフォーマンスを向上させ、その機能を強化するために実行できる手順があります。 これらの変更の詳細については、「 [ActiveX コントロール: Optimization](mfc-activex-controls-optimization.md)」を参照してください。

既存のコントロールに非同期プロパティのサポートを追加する場合は、準備完了状態プロパティとイベントを自分で追加する必要があり `ReadyStateChange` ます。 コントロールのコンストラクターで、次のように追加します。

[!code-cpp[NVC_MFCActiveXControl#8](codesnippet/cpp/activex-controls-on-the-internet_8.cpp)]

コードのダウンロード時には、 [COleControl:: InternalSetReadyState](reference/colecontrol-class.md#internalsetreadystate)を呼び出すことによって準備完了の状態を更新します。 を呼び出すことができる1つ `InternalSetReadyState` の場所は、 `OnProgress` の派生クラスのオーバーライドです `CDataPathProperty` 。

## <a name="see-also"></a>関連項目

[MFC インターネット プログラミングの作業](mfc-internet-programming-tasks.md)<br/>
[MFC インターネットプログラミングの基礎](mfc-internet-programming-basics.md)
