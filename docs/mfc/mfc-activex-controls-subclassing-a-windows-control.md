---
title: 'MFC ActiveX コントロール: Windows コントロールのサブクラス化 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- precreatewindow
- IsSubclassed
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e44366927cf5d17b5ec5edeebafb396b4e3f1b28
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929706"
---
# <a name="mfc-activex-controls-subclassing-a-windows-control"></a>MFC ActiveX コントロール : Windows コントロールのサブクラス化
この記事では、ActiveX コントロールを作成する一般的な Windows コントロールのサブクラス化するプロセスについて説明します。 既存のウィンドウをサブクラス化コントロールは、ActiveX コントロールを開発する簡単な方法です。 新しいコントロールの描画とマウスのクリックに応答してなどのサブクラス化された Windows コントロールの機能があります。 MFC ActiveX コントロールをサンプル[ボタン](../visual-cpp-samples.md)サブクラス化して、Windows コントロールの例に示します。  
  
 Windows コントロールをサブクラス化するには、次のタスクを行います。  
  
-   [COleControl の:issubclassedcontrol と PreCreateWindow メンバー関数をオーバーライドします。](#_core_overriding_issubclassedcontrol_and_precreatewindow)  
  
-   [このメンバー関数は OnDraw を変更します。](#_core_modifying_the_ondraw_member_function)  
  
-   [ActiveX コントロール メッセージ (OCM) をコントロールに反映を処理します。](#_core_handling_reflected_window_messages)  
  
    > [!NOTE]
    >  この作業の多くは自動的に実行で ActiveX コントロール ウィザードを使用してサブクラス化されたコントロールを選択した場合、**親ウィンドウ クラスの選択**ドロップダウン リストで、**制御設定**ページ。  
  
 コントロールのサブクラス化についての詳細については、サポート技術情報資料 Q243454 を参照してください。  
  
##  <a name="_core_overriding_issubclassedcontrol_and_precreatewindow"></a> :Issubclassedcontrol と PreCreateWindow のオーバーライド  
 オーバーライドする`PreCreateWindow`と`IsSubclassedControl`、コードの次の行を追加、**保護**コントロール クラス宣言のセクション。  
  
 [!code-cpp[NVC_MFC_AxSub#1](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_1.h)]  
  
 コントロール実装ファイル内 (です。CPP)、次の 2 つのオーバーライドされた関数を実装するコード行を追加します。  
  
 [!code-cpp[NVC_MFC_AxSub#2](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_2.cpp)]  
  
 この例と、Windows のボタン コントロールの通知がで指定された`PreCreateWindow`です。 ただし、その標準の Windows コントロールをサブクラス化できます。 標準の Windows コントロールの詳細については、次を参照してください。[コントロール](../mfc/controls-mfc.md)です。  
  
 Windows コントロールをサブクラス化場合は、特定のウィンドウ スタイル (ws _) またはコントロールのウィンドウの作成に使用する拡張ウィンドウ スタイル (WS_EX) フラグを指定することがあります。 これらのパラメーターの値を設定することができます、`PreCreateWindow`メンバー関数を変更して、`cs.style`と`cs.dwExStyle`フィールドを構成します。 使用してこれらのフィールドへの変更を確立する必要があります、**または**クラスによって設定される既定のフラグを保持するために、操作`COleControl`です。 たとえば、コントロールがボタン コントロールをサブクラス化し、チェック ボックスとして表示するコントロールする場合、この次のコード行の実装に挿入`CSampleCtrl::PreCreateWindow`、return ステートメントの前に。  
  
 [!code-cpp[NVC_MFC_AxSub#3](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_3.cpp)]  
  
 この操作は、クラスの既定のスタイル フラグ (WS_CHILD) 維持したまま、BS_CHECKBOX スタイル フラグを追加`COleControl`そのまま保持します。  
  
##  <a name="_core_modifying_the_ondraw_member_function"></a> OnDraw メンバー関数の変更  
 サブクラス コントロールを対応する Windows のコントロールと同じ外観を保持する場合、`OnDraw`コントロールのメンバー関数を呼び出す操作だけを含める必要があります、`DoSuperclassPaint`次の例のように、メンバー関数。  
  
 [!code-cpp[NVC_MFC_AxSub#4](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_4.cpp)]  
  
 `DoSuperclassPaint`によって実装されるメンバー関数`COleControl`、外接する四角形内の指定したデバイス コンテキストでコントロールを描画する Windows コントロールのウィンドウ プロシージャを使用します。 これにより、コントロールをアクティブになっていない場合でも表示できます。  
  
> [!NOTE]
>  `DoSuperclassPaint`メンバー関数はでしか動作として渡されるデバイス コンテキストをできるようにするコントロールの種類、 *wParam*が WM_PAINT メッセージのです。 これには、標準の Windows コントロールのスクロール バー ボタンとボタンなどの一部とすべての一般的なコントロールが含まれます。 この動作をサポートしないコントロールを非アクティブなコントロールを正しく表示するコードを指定する必要があります。  
  
##  <a name="_core_handling_reflected_window_messages"></a> 返送されたウィンドウ メッセージの処理  
 通常、Windows コントロールは、その親ウィンドウに特定のウィンドウ メッセージを送ります。 WM_COMMAND など、これらのメッセージの一部は、ユーザーが操作の通知を提供します。 他のユーザー、WM_CTLCOLOR などに使用されます、親ウィンドウから情報を取得します。 ActiveX コントロールは、通常、他の方法で、親ウィンドウと通信します。 通知は、(イベント通知を送信する)、イベントを発生させると、コンテナーのアンビエント プロパティにアクセスして、コントロール コンテナーに関する情報を取得します。 これらの通信技術存在するため、ActiveX コントロール コンテナーはコントロールによって送信されたウィンドウ メッセージを処理する必要はありません。  
  
 コンテナーが、Windows コントロールのサブクラスによって送信されたウィンドウ メッセージを受信するを防ぐため`COleControl`コントロールの親として機能する追加のウィンドウを作成します。 ActiveX コントロールのサブクラスが Windows を制御し、コントロールのウィンドウと同じサイズと位置を持っているに対してのみ、"reflector"と呼ばれるこの余分なウィンドウが作成されます。 Reflector ウィンドウは、特定のウィンドウ メッセージをインターセプトし、コントロールに返送します。 コントロールのウィンドウ プロシージャでは、(たとえば、イベントを発生させる) ActiveX コントロールの適切な操作を実行して返送されたメッセージを処理できます。 参照してください[ウィンドウ メッセージの Id を反映](../mfc/reflected-window-message-ids.md)傍受したウィンドウのリストのメッセージとそれに対応する反映されたメッセージ。  
  
 ActiveX コントロール コンテナーは必要がなくなるため、メッセージ リフレクションを実行するように設計することがあります`COleControl`reflector ウィンドウと実行時にサブクラス化された Windows コントロールのオーバーヘッドを減らすことを作成します。 `COleControl` 値を持つ MessageReflect アンビエント プロパティを確認する、コンテナーがこの機能をサポートしているかどうかを検出した**TRUE**です。  
  
 返送されたウィンドウ メッセージを処理するために、コントロール メッセージ マップ エントリを追加し、ハンドラー関数を実装します。 リフレクション メッセージは Windows によって定義されているメッセージの標準セットの一部ではないため、クラス ビューはこのようなメッセージ ハンドラーの追加サポートしていません。 ただし、ハンドラーを手動で追加するが困難はありません。  
  
 追加するには、メッセージのハンドラー返送されたウィンドウ メッセージを手動で、次を操作します。  
  
-   コントロール クラス。H ファイル ハンドラー関数を宣言します。 関数の戻り値の型を持つ必要があります**LRESULT**型で、2 つのパラメーターと**WPARAM**と**LPARAM**、それぞれします。 例えば:  
  
     [!code-cpp[NVC_MFC_AxSub#5](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_5.h)]  
    [!code-cpp[NVC_MFC_AxSub#6](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_6.h)]  
  
-   コントロール クラス。CPP ファイル、メッセージ マップに ON_MESSAGE エントリを追加します。 このエントリのパラメーターは、メッセージ識別子とハンドラー関数の名前にする必要があります。 例えば:  
  
     [!code-cpp[NVC_MFC_AxSub#7](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_7.cpp)]  
  
-   また、します。CPP ファイルの場合は、実装、`OnOcmCommand`反映されたメッセージを処理するメンバー関数。 *WParam*と*lParam*パラメーターでは、元のウィンドウ メッセージのものと同じです。  
  
 方法の例では、メッセージの処理を反映を参照してください、MFC ActiveX コントロールのサンプル[ボタン](../visual-cpp-samples.md)です。 示しています、 `OnOcmCommand` BN_CLICKED 通知コードを検出し、(送信) を発生させることによって応答ハンドラー、`Click`イベント。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)

