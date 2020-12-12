---
description: '詳細については、「MFC ActiveX コントロール: Windows コントロールのサブクラス化」を参照してください。'
title: 'MFC ActiveX コントロール : Windows コントロールのサブクラス化'
ms.date: 09/12/2018
f1_keywords:
- precreatewindow
- IsSubclassed
helpviewer_keywords:
- OnDraw method, MFC ActiveX controls
- subclassing
- DoSuperclassPaint method [MFC]
- subclassing Windows controls
- subclassing, Windows controls
- reflected messages, in ActiveX controls
- PreCreateWindow method, overriding
- MFC ActiveX controls [MFC], subclassed controls
- MFC ActiveX controls [MFC], creating
- IsSubclassed method [MFC]
ms.assetid: 3236d4de-401f-49b7-918d-c84559ecc426
ms.openlocfilehash: f3ea0e1af9860ca4585fe31817c689b75241d0f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164108"
---
# <a name="mfc-activex-controls-subclassing-a-windows-control"></a>MFC ActiveX コントロール : Windows コントロールのサブクラス化

この記事では、コモン Windows コントロールをサブクラス化して ActiveX コントロールを作成するプロセスについて説明します。 既存の Windows コントロールのサブクラスを作成すると、ActiveX コントロールを簡単に開発できます。 新しいコントロールは、サブクラス化された Windows コントロールの機能を備えています。たとえば、マウスクリックに対する描画や応答などです。 Windows コントロールのサブクラス化の例として、MFC ActiveX コントロールのサンプル [ボタン](../overview/visual-cpp-samples.md) があります。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX を置き換える最新テクノロジの詳細については、「 [Activex コントロール](activex-controls.md)」を参照してください。

Windows コントロールをサブクラス化するには、次のタスクを実行します。

- [COleControl の IsSubclassedControl および PreCreateWindow メンバー関数をオーバーライドします。](#_core_overriding_issubclassedcontrol_and_precreatewindow)

- [OnDraw メンバー関数を変更する](#_core_modifying_the_ondraw_member_function)

- [コントロールに反映された ActiveX コントロールメッセージ (OCM) を処理します](#_core_handling_reflected_window_messages)

   > [!NOTE]
   > この作業の大部分は、ActiveX コントロールウィザードによって、[**コントロールの設定**] ページの [**親ウィンドウクラスの選択**] ドロップダウンリストを使用してサブクラス化するコントロールを選択した場合に実行されます。

## <a name="overriding-issubclassedcontrol-and-precreatewindow"></a><a name="_core_overriding_issubclassedcontrol_and_precreatewindow"></a> IsSubclassedControl と PreCreateWindow のオーバーライド

およびをオーバーライドするには `PreCreateWindow` `IsSubclassedControl` 、 **`protected`** コントロールクラス宣言のセクションに次のコード行を追加します。

[!code-cpp[NVC_MFC_AxSub#1](codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_1.h)]

コントロールの実装ファイル (「」を指定します。CPP) で、次のコード行を追加して、オーバーライドされた2つの関数を実装します。

[!code-cpp[NVC_MFC_AxSub#2](codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_2.cpp)]

この例では、Windows ボタンコントロールがで指定されていることに注意して `PreCreateWindow` ください。 ただし、標準の Windows コントロールはすべてサブクラス化できます。 標準の Windows コントロールの詳細については、「 [コントロール](controls-mfc.md)」を参照してください。

Windows コントロールをサブクラス化するときに、コントロールのウィンドウの作成に使用する特定のウィンドウスタイル (WS_) または拡張ウィンドウスタイル (WS_EX_) フラグを指定することができます。 メンバー関数でこれらのパラメーターの値を設定する `PreCreateWindow` には、 `cs.style` および構造体のフィールドを変更し `cs.dwExStyle` ます。 これらのフィールドに対する変更は、クラスによって設定された既定のフラグを保持するために、 **または** 操作を使用して行う必要があり `COleControl` ます。 たとえば、コントロールがボタンコントロールをサブクラス化していて、コントロールがチェックボックスとして表示されるようにするには、次のコード行をの実装の `CSampleCtrl::PreCreateWindow` return ステートメントの前に挿入します。

[!code-cpp[NVC_MFC_AxSub#3](codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_3.cpp)]

この操作では、クラスの既定のスタイルフラグ (WS_CHILD) をそのまま残して、BS_CHECKBOX スタイルフラグを追加 `COleControl` します。

## <a name="modifying-the-ondraw-member-function"></a><a name="_core_modifying_the_ondraw_member_function"></a> OnDraw メンバー関数の変更

サブクラス化されたコントロールを、対応する Windows コントロールと同じ外観に保つには、 `OnDraw` 次の例のように、コントロールのメンバー関数にメンバー関数の呼び出しのみを含める必要があり `DoSuperclassPaint` ます。

[!code-cpp[NVC_MFC_AxSub#4](codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_4.cpp)]

`DoSuperclassPaint`によって実装されるメンバー関数は、 `COleControl` Windows コントロールのウィンドウプロシージャを使用して、指定されたデバイスコンテキストで、外接する四角形内にコントロールを描画します。 これにより、アクティブでない場合でもコントロールが表示されるようになります。

> [!NOTE]
> `DoSuperclassPaint`このメンバー関数は、デバイスコンテキストを WM_PAINT メッセージの *wParam* として渡すことができるようにするコントロール型でのみ機能します。 これには、SCROLLBAR や BUTTON などの標準の Windows コントロールと、すべての共通コントロールが含まれます。 この動作をサポートしないコントロールの場合は、非アクティブなコントロールを適切に表示するための独自のコードを用意する必要があります。

## <a name="handling-reflected-window-messages"></a><a name="_core_handling_reflected_window_messages"></a> 反映されたウィンドウメッセージの処理

Windows コントロールは、通常、特定のウィンドウメッセージを親ウィンドウに送信します。 WM_COMMAND など、これらのメッセージの一部は、ユーザーによるアクションの通知を提供します。 WM_CTLCOLOR などの他の情報は、親ウィンドウから情報を取得するために使用されます。 ActiveX コントロールは通常、他の方法で親ウィンドウと通信します。 通知はイベントの発生 (イベント通知の送信) によって伝達され、コントロールコンテナーに関する情報は、コンテナーのアンビエントプロパティにアクセスすることによって取得されます。 これらの通信方法は存在するため、ActiveX コントロールコンテナーでは、コントロールによって送信されたウィンドウメッセージを処理する必要はありません。

サブクラス化された Windows コントロールによって送信されたウィンドウメッセージをコンテナーが受信しないようにするために、は、 `COleControl` コントロールの親として機能する追加のウィンドウを作成します。 "リフレクター" と呼ばれるこの追加のウィンドウは、Windows コントロールのサブクラスであり、コントロールウィンドウと同じサイズと位置を持つ ActiveX コントロールに対してのみ作成されます。 リフレクタウィンドウは、特定のウィンドウメッセージをインターセプトし、コントロールに送り返します。 ウィンドウプロシージャ内のコントロールは、ActiveX コントロールに適切なアクション (イベントの発生など) を行うことによって、これらのリフレクションメッセージを処理できます。 インターセプトした windows メッセージの一覧とそれに対応するリフレクションメッセージの一覧については、「反映された [ウィンドウメッセージ id](reflected-window-message-ids.md) 」を参照してください。

ActiveX コントロールコンテナーは、メッセージリフレクション自体を実行するように設計されている場合があります。これにより、リフレクターウィンドウを作成し、サブクラス化された `COleControl` Windows コントロールの実行時のオーバーヘッドを減らす必要がなくなります。 `COleControl` 値が **TRUE** の MessageReflect アンビエントプロパティをチェックすることによって、コンテナーがこの機能をサポートするかどうかを検出します。

リフレクションされたウィンドウメッセージを処理するには、コントロールメッセージマップにエントリを追加し、ハンドラー関数を実装します。 リフレクションされたメッセージは、Windows で定義されている標準のメッセージセットの一部ではないため、クラスビューでは、このようなメッセージハンドラーの追加はサポートされていません。 ただし、ハンドラーを手動で追加することは困難です。

リフレクションされたウィンドウメッセージのメッセージハンドラーを手動で追加するには、次の手順を実行します。

- コントロールクラスの。H ファイル。ハンドラー関数を宣言します。 関数には、 **LRESULT** の戻り値の型と、 **WPARAM** および **LPARAM** 型の2つのパラメーターが必要です。 次に例を示します。

   [!code-cpp[NVC_MFC_AxSub#5](codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_5.h)]
    [!code-cpp[NVC_MFC_AxSub#6](codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_6.h)]

- コントロールクラスの。CPP ファイルで、メッセージマップに ON_MESSAGE エントリを追加します。 このエントリのパラメーターは、メッセージ識別子とハンドラー関数の名前にする必要があります。 次に例を示します。

   [!code-cpp[NVC_MFC_AxSub#7](codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_7.cpp)]

- にもあります。CPP ファイル `OnOcmCommand` 。リフレクションされたメッセージを処理するためのメンバー関数を実装します。 *WParam* と *lParam* のパラメーターは、元のウィンドウメッセージと同じです。

リフレクションされたメッセージの処理方法の例については、「MFC ActiveX コントロールのサンプル [ボタン」](../overview/visual-cpp-samples.md)を参照してください。 これは、 `OnOcmCommand` BN_CLICKED 通知コードを検出し、イベントを発生させる (送信する) ことによって応答するハンドラーを示して `Click` います。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](mfc-activex-controls.md)
