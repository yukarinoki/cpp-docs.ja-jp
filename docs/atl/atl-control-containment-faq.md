---
title: 'ATL コントロール コンテインメント : Q &amp; A 集'
ms.date: 11/04/2016
helpviewer_keywords:
- hosting controls using ATL
- ActiveX control containers [C++], ATL control hosting
- ATL, hosting ActiveX controls
- ActiveX controls [C++], hosting
- controls [ATL]
ms.assetid: d4bdfbe0-82ca-4f2f-bb95-cb89bdcc9b53
ms.openlocfilehash: 36ff3381447b46b28908522d65be9f34fe23addf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317397"
---
# <a name="atl-control-containment-faq"></a>ATL コントロール コンテインメント : Q &amp; A 集

## <a name="which-atl-classes-facilitate-activex-control-containment"></a>ActiveX コントロール コンテインメイトを助ける ATL クラスはどれか。

ATL のコントロール ホスト コードでは、ATL クラスを使用する必要はありません。**"AtlAxWin80"** ウィンドウを作成し、必要に応じてコントロール ホスティング API を使用することができます (詳細については **、「ATL コントロール ホスティング API とは」** を参照してください。 ただし、次のクラスは、コンテインメント機能を使いやすくします。

|クラス|説明|
|-----------|-----------------|
|[アクスウィンドウ](../atl/reference/caxwindow-class.md)|**"AtlAxWin80"** ウィンドウをラップし、ウィンドウの作成、コントロールの作成、ウィンドウへのコントロールのアタッチ、ホスト オブジェクトのインターフェイス ポインターの取得を行うためのメソッドを提供します。|
|[アクスウィンドウ2T](../atl/reference/caxwindow2t-class.md)|**"AtlAxWinLic80"** ウィンドウをラップし、ウィンドウの作成、コントロールの作成、およびウィンドウへのライセンス コントロールのアタッチ、およびホスト オブジェクトのインターフェイス ポインターの取得を行うためのメソッドを提供します。|
|[コンコムコンポジットコントロール](../atl/reference/ccomcompositecontrol-class.md)|ダイアログ リソースに基づいて ActiveX コントロール クラスの基本クラスとして機能します。 このようなコントロールには、他の ActiveX コントロールを含めることができます。|
|[アックスダイアログインプル](../atl/reference/caxdialogimpl-class.md)|ダイアログ リソースに基づいて、ダイアログ クラスの基本クラスとして機能します。 このようなダイアログには ActiveX コントロールを含めることができます。|
|[Cwindow](../atl/reference/cwindow-class.md)|ホスト ウィンドウの ID を指定して、コントロールのインターフェイス ポインターを返すメソッド[GetDlgControl](../atl/reference/cwindow-class.md#getdlgcontrol)を提供します。 また、Windows API ラッパーは一般に`CWindow`ウィンドウ管理を容易にします。|

## <a name="what-is-the-atl-control-hosting-api"></a>ATL コントロール ホスト API とは何か。

ATL のコントロール ホスト API は、任意のウィンドウが ActiveX コントロール コンテナーとして機能することを可能にする関数のセットです。 これらの関数は、ソース コードとして使用でき、ATL90.dll によって公開されるため、プロジェクトに静的または動的にリンクできます。 コントロール ホスティング関数は、次の表に示します。

|機能|説明|
|--------------|-----------------|
|[AtlAxAttachControl](reference/composite-control-global-functions.md#atlaxattachcontrol)|ホスト オブジェクトを作成し、指定されたウィンドウに接続してから、既存のコントロールをアタッチします。|
|[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)|ホスト オブジェクトを作成し、指定されたウィンドウに接続してから、コントロールを読み込みます。|
|[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)|ライセンスを取得した ActiveX コントロールを作成し、初期化し、指定されたウィンドウで[ホストします。](reference/composite-control-global-functions.md#atlaxcreatecontrol)|
|[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)|ホスト オブジェクトを作成し、指定されたウィンドウに接続してからコントロールを読み込みます (イベント シンクの設定も可能)。|
|[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrollicex)|ライセンスを取得した ActiveX コントロールを作成し、初期化し、指定されたウィンドウで[ホストします。](reference/composite-control-global-functions.md#atlaxcreatecontrollic)|
|[AtlAxCreateDialog](reference/composite-control-global-functions.md#atlaxcreatedialog)|ダイアログ リソースからモードレス ダイアログ ボックスを作成し、ウィンドウ ハンドルを返します。|
|[AtlAxDialogBox](reference/composite-control-global-functions.md#atlaxdialogbox)|ダイアログ リソースからモーダル ダイアログ ボックスを作成します。|
|[AtlAxGetControl](reference/composite-control-global-functions.md#atlaxgetcontrol)|ウィンドウでホストされているコントロールの**IUnknown**インターフェイス ポインターを返します。|
|[AtlAxGetHost](reference/composite-control-global-functions.md#atlaxgethost)|ウィンドウに接続されているホスト オブジェクトの**IUnknown**インターフェイス ポインターを返します。|
|[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit)|コントロールをホストするコードを初期化します。|
|[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm)|コントロールホストコードの初期化を解除します。|

最初`HWND`の 3 つの関数のパラメーターは、(ほぼ) すべての型の既存のウィンドウである必要があります。 これら 3 つの関数のいずれかを明示的に呼び出す場合 (通常は、必要はありません)、既にホストとして機能しているウィンドウにハンドルを渡しません (ホストとして機能している場合、既存のホスト オブジェクトは解放されません)。

最初の 7 つの関数は[、暗黙的に AtlAxWinInit を](reference/composite-control-global-functions.md#atlaxwininit)呼び出します。

> [!NOTE]
> コントロール ホスト API は、ATL による ActiveX コントロールコンテインメントのサポートの基礎となります。 しかし、ATL のラッパー クラスを利用したり、フルに利用したりする場合、通常、これらの関数を直接呼び出す必要はほとんどありません。 詳細については、「 [ActiveX コントロールの格納を容易にする ATL クラス 」](which-atl-classes-facilitate-activex-control-containment-q.md)を参照してください。

## <a name="what-is-atlaxwin100"></a>AtlAxWin100 とは何か。

`AtlAxWin100`は、ATL のコントロール ホスト機能を提供するウィンドウ クラスの名前です。 このクラスのインスタンスを作成すると、ウィンドウ プロシージャは自動的にコントロール ホスト API を使用して、ウィンドウに関連付けられたホスト オブジェクトを作成し、ウィンドウのタイトルとして指定したコントロールと共に読み込みます。

## <a name="when-do-i-need-to-call-atlaxwininit"></a>AtlAxWinInit はいつ呼び出す必要があるのか。

[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit)は **、"AtlAxWin80"** ウィンドウ クラス (およびカスタム ウィンドウ メッセージの 2 つ) を登録するため、ホスト ウィンドウを作成する前にこの関数を呼び出す必要があります。 ただし、ホスト API (および API を使用するクラス) は頻繁にこの関数を呼び出すため、この関数を明示的に呼び出す必要はありません。 この関数を複数回呼び出しても、害はありません。

## <a name="what-is-a-host-object"></a>ホスト オブジェクトとは何か。

ホスト オブジェクトは、特定のウィンドウに対して ATL によって提供される ActiveX コントロール コンテナーを表す COM オブジェクトです。 ホスト オブジェクトは、コントロールにメッセージを反映できるようにコンテナー ウィンドウをサブクラス化し、コントロールで使用する必要なコンテナー インターフェイスを提供し、コントロールの環境を構成できるように[IAxWinHostWindow](../atl/reference/iaxwinhostwindow-interface.md)インターフェイスと[IAxWinAmbientDispatch](../atl/reference/iaxwinambientdispatch-interface.md)インターフェイスを公開します。

ホスト オブジェクトを使用して、コンテナーのアンビエント プロパティを設定できます。

## <a name="can-i-host-more-than-one-control-in-a-single-window"></a>1 つのウィンドウで複数のコントロールをホストできるか。

1 つの ATL ホスト ウィンドウで複数のコントロールをホストすることはできません。 各ホスト ウィンドウは、一度に 1 つのコントロールを保持するように設計されています (これにより、メッセージのリフレクションとコントロールごとのアンビエント プロパティを処理するための簡単なメカニズムが可能になります)。 ただし、ユーザーが 1 つのウィンドウに複数のコントロールを表示する必要がある場合は、そのウィンドウの子として複数のホスト ウィンドウを作成するのは簡単な問題です。

## <a name="can-i-reuse-a-host-window"></a>ホスト ウィンドウを再利用できるか。

ホスト ウィンドウを再利用することはお勧めできません。 コードの堅牢性を確保するには、ホスト ウィンドウの有効期間を 1 つのコントロールの有効期間に結び付ける必要があります。

## <a name="when-do-i-need-to-call-atlaxwinterm"></a>AtlAxWinTerm はいつ呼び出す必要があるのか。

[ウィンドウ](reference/composite-control-global-functions.md#atlaxwinterm)クラスを**登録**解除します。 既存のホスト ウィンドウがすべて破棄された後に、この関数を呼び出す必要があります (ホスト ウィンドウを作成する必要がなくなった場合)。 この関数を呼び出さないと、プロセスが終了するとウィンドウ クラスは自動的に登録解除されます。

## <a name="hosting-activex-controls-using-atl-axhost"></a>ATL AXHost を使用して ActiveX コントロールをホストする

このセクションのサンプルでは、AXHost を作成する方法と、さまざまな ATL 関数を使用して ActiveX コントロールをホストする方法を示します。 また、ホストされているコントロールからコントロールにアクセスし、[イベントをシンク](../atl/reference/idispeventimpl-class.md)する方法も示します 。 このサンプルでは、Calendar コントロールをメイン ウィンドウまたは子ウィンドウでホストしています。

シンボルの定義に`USE_METHOD`注目してください。 このシンボルの値は、1 ~ 8 の間で変化するように変更できます。 シンボルの値によって、コントロールの作成方法が決まります。

- 偶数の値の`USE_METHOD`場合、ホストを作成する呼び出しはウィンドウをサブクラス化し、それをコントロールホストに変換します。 奇数の値の場合、コードはホストとして機能する子ウィンドウを作成します。

- 1 から`USE_METHOD`4 までの値の場合、ホストを作成する呼び出しでは、コントロールへのアクセスとイベントのシンクが行われます。 5 ~ 8 の値は、ホストにインターフェイスを照会し、シンクをフックします。

次に概要を示します。

|USE_METHOD|Host|アクセスとイベントのシンクを制御する|関数の実演|
|-----------------|----------|--------------------------------------|---------------------------|
|1|子ウィンドウ|ワンステップ|コントロールスライスを作成します。|
|2|メイン ウィンドウ|ワンステップ|AtlAxCreateControlLicEx|
|3|子ウィンドウ|ワンステップ|コントロールエックスを作成する|
|4|メイン ウィンドウ|ワンステップ|AtlAxCreateControlEx|
|5|子ウィンドウ|複数のステップ|コントロールコントロールの作成|
|6|メイン ウィンドウ|複数のステップ|AtlAxCreateControlLic|
|7|子ウィンドウ|複数のステップ|CreateControl|
|8|メイン ウィンドウ|複数のステップ|AtlAxCreateControl|

[!code-cpp[NVC_ATL_AxHost#1](../atl/codesnippet/cpp/hosting-activex-controls-using-atl-axhost_1.cpp)]

## <a name="see-also"></a>関連項目

[コントロール コンテインメント : Q &amp; A 集](../atl/atl-control-containment-faq.md)<br/>
[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)<br/>
[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)<br/>
[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)<br/>
[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)<br/>
[クラス](../atl/reference/caxwindow2t-class.md)<br/>
[インターフェイス](../atl/reference/iaxwinhostwindowlic-interface.md)
