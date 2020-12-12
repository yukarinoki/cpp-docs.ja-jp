---
description: '詳細情報: ATL コントロールコンテインメントに関する FAQ'
title: 'ATL コントロール コンテインメント : Q &amp; A 集'
ms.date: 11/04/2016
helpviewer_keywords:
- hosting controls using ATL
- ActiveX control containers [C++], ATL control hosting
- ATL, hosting ActiveX controls
- ActiveX controls [C++], hosting
- controls [ATL]
ms.assetid: d4bdfbe0-82ca-4f2f-bb95-cb89bdcc9b53
ms.openlocfilehash: 5c5d3d452a119908cb6c8dcdb08da3276db78f51
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165772"
---
# <a name="atl-control-containment-faq"></a>ATL コントロール コンテインメント : Q &amp; A 集

## <a name="which-atl-classes-facilitate-activex-control-containment"></a>ActiveX コントロール コンテインメイトを助ける ATL クラスはどれか。

ATL のコントロールホストコードでは、ATL クラスを使用する必要はありません。単純に **"AtlAxWin80"** ウィンドウを作成し、必要に応じてコントロールホスト API を使用できます (詳細については、「 **ATL Control-Hosting api とは**」を参照してください)。 ただし、次のクラスを使用すると、コンテインメント機能が簡単に使用できるようになります。

|クラス|説明|
|-----------|-----------------|
|[CAxWindow](../atl/reference/caxwindow-class.md)|**"AtlAxWin80"** ウィンドウをラップして、ウィンドウを作成したり、コントロールを作成したり、ウィンドウにコントロールをアタッチしたり、ホストオブジェクトのインターフェイスポインターを取得したりするためのメソッドを提供します。|
|[CAxWindow2T](../atl/reference/caxwindow2t-class.md)|**"AtlAxWinLic80"** ウィンドウをラップして、ウィンドウを作成したり、コントロールを作成したり、ライセンスされたコントロールをウィンドウにアタッチしたり、ホストオブジェクトのインターフェイスポインターを取得したりするためのメソッドを提供します。|
|[CComCompositeControl](../atl/reference/ccomcompositecontrol-class.md)|ダイアログリソースに基づく ActiveX コントロールクラスの基底クラスとして機能します。 このようなコントロールには、他の ActiveX コントロールを含めることができます。|
|[CAxDialogImpl](../atl/reference/caxdialogimpl-class.md)|ダイアログリソースに基づくダイアログクラスの基本クラスとして機能します。 このようなダイアログには、ActiveX コントロールを含めることができます。|
|[CWindow](../atl/reference/cwindow-class.md)|ホストウィンドウの ID を指定して、コントロールにインターフェイスポインターを返す、 [Getdlgcontrol](../atl/reference/cwindow-class.md#getdlgcontrol)メソッドを提供します。 また、によって公開される Windows API ラッパーは、 `CWindow` 一般にウィンドウの管理を容易にします。|

## <a name="what-is-the-atl-control-hosting-api"></a>ATL コントロール ホスト API とは何か。

ATL のコントロールホスト API は、任意のウィンドウが ActiveX コントロールコンテナーとして機能することを許可する関数のセットです。 これらの関数は、ソースコードとして使用でき、ATL90.dll によって公開されるため、プロジェクトに静的または動的にリンクできます。 次の表に、コントロールホスト関数の一覧を示します。

|機能|説明|
|--------------|-----------------|
|[AtlAxAttachControl](reference/composite-control-global-functions.md#atlaxattachcontrol)|ホストオブジェクトを作成し、指定されたウィンドウに接続して、既存のコントロールをアタッチします。|
|[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)|ホストオブジェクトを作成し、指定されたウィンドウに接続して、コントロールを読み込みます。|
|[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)|ライセンスされた ActiveX コントロールを作成して初期化し、 [AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)と同様に、指定したウィンドウでホストします。|
|[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)|ホストオブジェクトを作成し、指定されたウィンドウに接続して、コントロールを読み込みます (イベントシンクも設定できます)。|
|[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrollicex)|ライセンスされた ActiveX コントロールを作成して初期化し、 [AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)と同様に、指定したウィンドウでホストします。|
|[AtlAxCreateDialog](reference/composite-control-global-functions.md#atlaxcreatedialog)|ダイアログリソースからモードレスダイアログボックスを作成し、ウィンドウハンドルを返します。|
|[AtlAxDialogBox](reference/composite-control-global-functions.md#atlaxdialogbox)|ダイアログリソースからモーダルダイアログボックスを作成します。|
|[AtlAxGetControl](reference/composite-control-global-functions.md#atlaxgetcontrol)|ウィンドウでホストされているコントロールの **IUnknown** インターフェイスポインターを返します。|
|[AtlAxGetHost](reference/composite-control-global-functions.md#atlaxgethost)|ウィンドウに接続されているホストオブジェクトの **IUnknown** インターフェイスポインターを返します。|
|[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit)|コントロールホストコードを初期化します。|
|[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm)|コントロールホストコードを初期化前します。|

`HWND`最初の3つの関数のパラメーターは、(ほぼ) 任意の型の既存のウィンドウである必要があります。 これら3つの関数のいずれかを明示的に呼び出すと (通常は必要ありません)、既にホストとして機能しているウィンドウにハンドルを渡さないでください (実行すると、既存のホストオブジェクトは解放されません)。

最初の7つの関数は、暗黙的に [AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) を呼び出します。

> [!NOTE]
> コントロールホスト API は、ATL の ActiveX コントロールコンテインメントのサポートの基礎を形成します。 ただし、ATL のラッパークラスを使用するか、完全に使用する場合は、通常、これらの関数を直接呼び出す必要はほとんどありません。 詳細については、「 [ActiveX コントロールのコンテインメントを容易にする ATL クラス](#which-atl-classes-facilitate-activex-control-containment)」を参照してください。

## <a name="what-is-atlaxwin100"></a>AtlAxWin100 とは何か。

`AtlAxWin100` は、ATL のコントロールのホスト機能を提供するために役立つウィンドウクラスの名前です。 このクラスのインスタンスを作成すると、ウィンドウプロシージャは自動的にコントロールホスティング API を使用して、ウィンドウに関連付けられたホストオブジェクトを作成し、ウィンドウのタイトルとして指定したコントロールと共に読み込みます。

## <a name="when-do-i-need-to-call-atlaxwininit"></a>AtlAxWinInit はいつ呼び出す必要があるのか。

[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) は、 **"AtlAxWin80"** ウィンドウクラス (およびいくつかのカスタムウィンドウメッセージ) を登録するため、ホストウィンドウを作成する前にこの関数を呼び出す必要があります。 ただし、この関数を明示的に呼び出す必要はありません。これは、ホスト Api (およびそれらを使用するクラス) が頻繁にこの関数を呼び出すためです。 この関数を複数回呼び出すことには害がありません。

## <a name="what-is-a-host-object"></a>ホスト オブジェクトとは何か。

ホストオブジェクトは、特定のウィンドウに対して ATL によって提供される ActiveX コントロールコンテナーを表す COM オブジェクトです。 ホストオブジェクトは、コンテナーウィンドウをサブクラス化して、コントロールへのメッセージを反映できるようにします。また、コントロールによって使用されるために必要なコンテナーインターフェイスを提供します。また、コントロールの環境を構成できるように、 [IAxWinHostWindow](../atl/reference/iaxwinhostwindow-interface.md) インターフェイスと [IAxWinAmbientDispatch](../atl/reference/iaxwinambientdispatch-interface.md) インターフェイスを公開します。

ホストオブジェクトを使用して、コンテナーのアンビエントプロパティを設定できます。

## <a name="can-i-host-more-than-one-control-in-a-single-window"></a>1 つのウィンドウで複数のコントロールをホストできるか。

1つの ATL ホストウィンドウで複数のコントロールをホストすることはできません。 各ホストウィンドウは、一度に1つのコントロールだけを保持するように設計されています (これにより、メッセージのリフレクションとコントロールごとのアンビエントプロパティを簡単に処理できます)。 ただし、ユーザーが複数のコントロールを1つのウィンドウに表示する必要がある場合は、そのウィンドウの子として複数のホストウィンドウを作成するのが簡単です。

## <a name="can-i-reuse-a-host-window"></a>ホスト ウィンドウを再利用できるか。

ホストウィンドウを再利用することはお勧めしません。 コードの堅牢性を確保するには、ホストウィンドウの有効期間を1つのコントロールの有効期間に関連付ける必要があります。

## <a name="when-do-i-need-to-call-atlaxwinterm"></a>AtlAxWinTerm はいつ呼び出す必要があるのか。

[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm) は、 **"AtlAxWin80"** ウィンドウクラスの登録を解除します。 既存のすべてのホストウィンドウが破棄された後に、この関数を呼び出す必要があります (ホストウィンドウを作成する必要がなくなった場合)。 この関数を呼び出さない場合、プロセスの終了時にウィンドウクラスが自動的に登録解除されます。

## <a name="hosting-activex-controls-using-atl-axhost"></a>ATL AXHost を使用して ActiveX コントロールをホストする

このセクションのサンプルでは、AXHost を作成する方法と、さまざまな ATL 関数を使用して ActiveX コントロールをホストする方法を示します。 また、ホストされているコントロールから、( [IDispEventImpl](../atl/reference/idispeventimpl-class.md)を使用して) コントロールとシンクイベントにアクセスする方法も示します。 このサンプルでは、メインウィンドウまたは子ウィンドウで Calendar コントロールをホストします。

シンボルの定義を確認 `USE_METHOD` します。 この記号の値は、1 ~ 8 の範囲で変更できます。 シンボルの値によって、コントロールの作成方法が決まります。

- の偶数の値については `USE_METHOD` 、ホストを作成するための呼び出しによってウィンドウがサブクラス化され、コントロールホストに変換されます。 奇数の値の場合、コードはホストとして機能する子ウィンドウを作成します。

- 1 ~ 4 の値の場合 `USE_METHOD` 、コントロールへのアクセスとイベントのシンクは、ホストも作成する呼び出しで実行されます。 5 ~ 8 の値は、ホストでインターフェイスを照会し、シンクをフックします。

次に概要を示します。

|USE_METHOD|ホスト|アクセスとイベントシンクの制御|関数のデモンストレーション|
|-----------------|----------|--------------------------------------|---------------------------|
|1|子ウィンドウ|1つの手順|CreateControlLicEx|
|2|メイン ウィンドウ|1つの手順|AtlAxCreateControlLicEx|
|3|子ウィンドウ|1つの手順|CreateControlEx|
|4|メイン ウィンドウ|1つの手順|AtlAxCreateControlEx|
|5|子ウィンドウ|複数の手順|CreateControlLic|
|6|メイン ウィンドウ|複数の手順|AtlAxCreateControlLic|
|7|子ウィンドウ|複数の手順|CreateControl|
|8|メイン ウィンドウ|複数の手順|AtlAxCreateControl|

[!code-cpp[NVC_ATL_AxHost#1](../atl/codesnippet/cpp/hosting-activex-controls-using-atl-axhost_1.cpp)]

## <a name="see-also"></a>関連項目

[コントロール コンテインメント : Q &amp; A 集](../atl/atl-control-containment-faq.md)<br/>
[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)<br/>
[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)<br/>
[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)<br/>
[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)<br/>
[CAxWindow2T クラス](../atl/reference/caxwindow2t-class.md)<br/>
[IAxWinHostWindowLic インターフェイス](../atl/reference/iaxwinhostwindowlic-interface.md)
