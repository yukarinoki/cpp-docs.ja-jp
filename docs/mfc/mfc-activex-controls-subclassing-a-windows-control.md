---
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
ms.openlocfilehash: ccebbad22be92b84fa2fd84434f788484d332cce
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375994"
---
# <a name="mfc-activex-controls-subclassing-a-windows-control"></a>MFC ActiveX コントロール : Windows コントロールのサブクラス化

この資料では、一般的な Windows コントロールをサブクラス化して ActiveX コントロールを作成するプロセスについて説明します。 既存の Windows コントロールをサブクラス化すると、ActiveX コントロールを簡単に開発できます。 新しいコントロールには、描画やマウスクリックへの応答など、サブクラス化された Windows コントロールの機能があります。 MFC ActiveX コントロールのサンプル[ボタン](../overview/visual-cpp-samples.md)は、Windows コントロールのサブクラス化の例です。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX に取って代わる最新テクノロジの詳細については、「 [ActiveX コントロール](activex-controls.md)」を参照してください。

Windows コントロールをサブクラス化するには、次のタスクを実行します。

- [をオーバーライドする、コントロールのクラス化コントロールとプレCreateウィンドウのメンバー関数](#_core_overriding_issubclassedcontrol_and_precreatewindow)

- [OnDraw メンバー関数を変更します。](#_core_modifying_the_ondraw_member_function)

- [コントロールに反映された ActiveX コントロール メッセージ (OCM) を処理します。](#_core_handling_reflected_window_messages)

   > [!NOTE]
   > この作業の多くは、[コントロールの**設定]** ページの **[親ウィンドウ クラスの選択**] ボックスの一覧を使用してサブクラス化するコントロールを選択した場合に、ActiveX コントロール ウィザードによって行われます。

## <a name="overriding-issubclassedcontrol-and-precreatewindow"></a><a name="_core_overriding_issubclassedcontrol_and_precreatewindow"></a>オーバーライドするクラス化されたコントロールとプレCreateウィンドウ

を`IsSubclassedControl`オーバーライド`PreCreateWindow`するには、コントロール クラス宣言の**保護された**セクションに次のコード行を追加します。

[!code-cpp[NVC_MFC_AxSub#1](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_1.h)]

コントロール実装ファイル (.CPP) を追加するコードの次の行は、オーバーライドされた 2 つの関数を実装します。

[!code-cpp[NVC_MFC_AxSub#2](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_2.cpp)]

この例では、Windows ボタン コントロールが で指定されていること`PreCreateWindow`に注意してください。 ただし、標準の Windows コントロールは、サブクラス化できます。 Windows 標準のコントロールの詳細については、「[コントロール](../mfc/controls-mfc.md)」を参照してください。

Windows コントロールをサブクラス化する場合、コントロールのウィンドウの作成に使用する特定のウィンドウ スタイル (WS_) または拡張ウィンドウ スタイル (WS_EX_) フラグを指定できます。 これらのパラメーターの値は、 `PreCreateWindow` `cs.style`および 構造体フィールドを変更することで、メンバー関数`cs.dwExStyle`で設定できます。 これらのフィールドに対する変更は OR**演算を**使用して行い、class`COleControl`で設定されたデフォルトのフラグを保持する必要があります。 たとえば、コントロールが BUTTON コントロールをサブクラス化していて、コントロールをチェック ボックスとして表示する場合は、return ステートメントの前に次の`CSampleCtrl::PreCreateWindow`コード行を の実装に挿入します。

[!code-cpp[NVC_MFC_AxSub#3](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_3.cpp)]

この操作では、BS_CHECKBOXスタイル フラグを追加し、クラス`COleControl`の既定のスタイル フラグ (WS_CHILD) をそのまま残します。

## <a name="modifying-the-ondraw-member-function"></a><a name="_core_modifying_the_ondraw_member_function"></a>OnDraw メンバー関数の変更

サブクラス化されたコントロールが対応する Windows コントロールと同じ外観を維持する場合`OnDraw`は、次の例のように、コントロールの`DoSuperclassPaint`メンバー関数にメンバー関数の呼び出しのみを含める必要があります。

[!code-cpp[NVC_MFC_AxSub#4](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_4.cpp)]

によって`DoSuperclassPaint``COleControl`実装されるメンバー関数は、Windows コントロールのウィンドウ プロシージャを使用して、指定したデバイス コンテキスト内の、外接する四角形内のコントロールを描画します。 これにより、アクティブでない場合でもコントロールが表示されます。

> [!NOTE]
> `DoSuperclassPaint`このメンバー関数は、デバイス コンテキストを WM_PAINT メッセージの*wParam*として渡すことを許可するコントロール型でのみ動作します。 これには、スクロール バーやボタンなどの Windows 標準コントロールと、すべてのコモン コントロールが含まれます。 この動作をサポートしていないコントロールの場合は、非アクティブなコントロールを正しく表示するために、独自のコードを用意する必要があります。

## <a name="handling-reflected-window-messages"></a><a name="_core_handling_reflected_window_messages"></a>リフレクションされたウィンドウ メッセージの処理

Windows コントロールは通常、特定のウィンドウ メッセージを親ウィンドウに送信します。 WM_COMMANDなどのこれらのメッセージの一部は、ユーザーによるアクションの通知を提供します。 WM_CTLCOLORなどの他のユーザーは、親ウィンドウから情報を取得するために使用されます。 ActiveX コントロールは、通常、親ウィンドウと通信する方法を使用します。 通知はイベントを発生させることによって通知され (イベント通知を送信する)、コントロール コンテナーに関する情報は、コンテナーのアンビエント プロパティにアクセスすることによって取得されます。 これらの通信手法が存在するため、ActiveX コントロール コンテナーは、コントロールによって送信されるウィンドウ メッセージを処理する必要はありません。

サブクラス化された Windows コントロールから送信されたウィンドウ メッセージをコンテナが受信`COleControl`しないようにするには、コントロールの親として機能する追加のウィンドウを作成します。 この追加ウィンドウは、"リフレクタ" と呼ばれ、Windows コントロールのサブクラスを作成する ActiveX コントロールに対してのみ作成され、コントロール ウィンドウと同じサイズと位置を持ちます。 リフレクター ウィンドウは、特定のウィンドウ メッセージをインターセプトし、コントロールに返します。 そのウィンドウ プロシージャ内のコントロールは、ActiveX コントロールに適したアクションを実行してこれらの反映メッセージを処理できます (イベントの発生など)。 インターセプトされたウィンドウ メッセージと対応するリフレクション メッセージの一覧については、「[リフレクション](../mfc/reflected-window-message-ids.md)ウィンドウ メッセージ ID」を参照してください。

ActiveX コントロール コンテナーは、メッセージのリフレクション自体を実行するように設計されている`COleControl`場合があります。 `COleControl`値 TRUE の MessageReflect アンビエント プロパティをチェックして、コンテナーがこの機能をサポートしているかどうかを**検出します。**

リフレクションされたウィンドウ メッセージを処理するには、コントロール メッセージ マップにエントリを追加し、ハンドラー関数を実装します。 リフレクション メッセージは Windows で定義された標準メッセージ セットの一部ではないため、クラス ビューではこのようなメッセージ ハンドラーの追加はサポートされていません。 ただし、ハンドラーを手動で追加することは難しいわけではありません。

リフレクション ウィンドウ メッセージのメッセージ ハンドラーを手動で追加するには、次の操作を行います。

- コントロール クラスで.H ファイルは、ハンドラー関数を宣言します。 この関数は **、それぞれ、LRESULT**の戻り値の型と **、WPARAM**と**LPARAM**の 2 つのパラメーターを持つ必要があります。 次に例を示します。

   [!code-cpp[NVC_MFC_AxSub#5](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_5.h)]
    [!code-cpp[NVC_MFC_AxSub#6](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_6.h)]

- コントロール クラスで.CPP ファイルを表示するには、メッセージ マップにON_MESSAGEエントリを追加します。 このエントリのパラメータは、メッセージ識別子とハンドラ関数の名前にする必要があります。 次に例を示します。

   [!code-cpp[NVC_MFC_AxSub#7](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_7.cpp)]

- また、 .CPP ファイルは、`OnOcmCommand`反映されたメッセージを処理するメンバー関数を実装します。 *wParam*と*lParam*パラメータは、元のウィンドウ メッセージと同じです。

リフレクション メッセージの処理方法の例については、MFC ActiveX コントロールのサンプル[BUTTON](../overview/visual-cpp-samples.md)を参照してください。 BN_CLICKED通知コードを`OnOcmCommand`検出し、イベントを発生 (送信) して応答するハンドラーを`Click`示します。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)
