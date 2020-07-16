---
title: '[コントロールの設定] (MFC ActiveX コントロール ウィザード)'
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.ctl.settings
helpviewer_keywords:
- MFC ActiveX Control Wizard, control settings
ms.assetid: 2ccaa4fc-0d52-413e-afa3-ecd474c3f6f0
ms.openlocfilehash: 1578ca7f4134e51e0ba0d3c2b247dcafcb0fbd67
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "86405014"
---
# <a name="control-settings-mfc-activex-control-wizard"></a>[コントロールの設定] (MFC ActiveX コントロール ウィザード)

ウィザードのこのページを使用して、コントロールの動作を指定します。 たとえば、標準の Windows コントロール型に基づいてコントロールを作成し、その動作と外観を最適化することができます。また、コントロールが他のコントロールのコンテナーとして機能することを示すこともできます。

このページのオプションを選択してコントロールの効率を最大化する方法の詳細については、「 [MFC ActiveX コントロール: 最適化](../../mfc/mfc-activex-controls-optimization.md)」を参照してください。

## <a name="uielement-list"></a>UIElement の一覧

- **に基づいてコントロールを作成する**

   この一覧では、コントロールの継承元となるコントロールの種類を選択できます。 リストは、で使用できるコントロールクラスのサブセットであり、 `CreateWindowEx` commctrl. h で指定されている追加のコモンコントロールです。 選択すると、 `PreCreateWindow` *ProjName*Ctrl .cpp ファイル内の関数のコントロールのスタイルが決まります。 詳細については、「 [MFC ActiveX コントロール: Windows コントロールのサブクラス](../../mfc/mfc-activex-controls-subclassing-a-windows-control.md)化」を参照してください。

   |コントロール|説明|
   |-------------|-----------------|
   |**;**|Windows のボタンコントロール|
   |**COMBOBOX**|Windows コンボボックスコントロール|
   |**編集**|Windows エディットボックスコントロール|
   |**LISTBOX**|Windows リストボックスコントロール|
   |**SCROLLBAR**|Windows スクロールバーコントロール|
   |**雑音**|Windows スタティックコントロール|
   |**msctls_hotkey32**|ホットキーコモンコントロール|
   |**msctls_progress32**|プログレスバーのコモンコントロール|
   |**msctls_statusbar32**|ステータスバーコモンコントロール|
   |**msctls_trackbar32**|トラックバーのコモンコントロール|
   |**msctls_updown32**|スピンボタン (またはアップダウン) コモンコントロール|
   |**SysAnimate32**|アニメーションコモンコントロール|
   |**SysHeader32**|ヘッダーコモンコントロール|
   |**SysListView32**|リストビューコモンコントロール|
   |**SysTabControl32**|タブコモンコントロール|
   |**SysTreeView32**|ツリービューのコモンコントロール|

- **表示時にアクティブにする**

   アクセス時にコントロールに対してウィンドウを作成することを指定します。 既定では、[**表示時にアクティブにする**] オプションが選択されています。 コンテナーが必要とするまで (たとえば、ユーザーがマウスをクリックしたときに) コントロールのアクティブ化を延期する場合は、このオプションをオフにします。 この機能がオフになっていると、コントロールは必要になるまでウィンドウ作成の費用を発生させません。 詳細については、「 [[表示時にアクティブ化] オプションをオフ](../../mfc/turning-off-the-activate-when-visible-option.md)にする」を参照してください。

- **実行時に非表示**

   コントロールが実行時にユーザーインターフェイスを持たないことを指定します。 タイマーは、非表示にすることができるコントロールの一種です。

- **[バージョン情報] ボックスダイアログがある**

   コントロールに、バージョン番号と著作権情報を表示する標準の [Windows バージョン**情報**] ダイアログボックスがあることを指定します。

   > [!NOTE]
   > ユーザーがコントロールのヘルプにアクセスする方法は、ヘルプの実装方法、およびコントロールをコンテナーのヘルプと統合したかどうかによって異なります。

   このオプションを選択すると、 `AboutBox` プロジェクトコントロールクラス (C*ProjName*Ctrl .cpp) にコントロールメソッドが挿入され、AboutBox がプロジェクトディスパッチマップに追加されます。 既定では、このオプションが選択されています。

- **最適化された描画コード**

   同じデバイスコンテキストに描画されるすべてのコンテナーコントロールが描画された後に、コンテナーが元の GDI オブジェクトを自動的に復元するように指定します。 この機能の詳細については、「[コントロールの描画の最適化](../../mfc/optimizing-control-drawing.md)」を参照してください。

- **ウィンドウなしのアクティブ化**

   コントロールがアクティブになったときに、ウィンドウを生成しないように指定します。 ウィンドウなしのアクティベーションは、四角形なしまたは透明なコントロールを許可します。ウィンドウなしのコントロールでは、ウィンドウが必要なコントロールよりもシステムオーバーヘッドが少なくて済みます。 ウィンドウなしのコントロールでは、クリッピングを行わないデバイスコンテキストやちらつきなしのアクティベーションを行うことはできません。 1996より前に作成されたコンテナーは、ウィンドウなしのアクティベーションをサポートしていません。 このオプションの使用方法の詳細については、「[ウィンドウなしのアクティベーションの提供](../../mfc/providing-windowless-activation.md)」を参照してください。

- **クリッピングを行っていないデバイスコンテキスト**

   は、コントロールヘッダー (*projname*ctrl. h) の[COleControl:: getcontrolflags](../../mfc/reference/colecontrol-class.md#getcontrolflags)をオーバーライドして、による呼び出しを無効にし `IntersectClipRect` `COleControl` ます。 このオプションを選択すると、小さい速度の利点が得られます。 [**ウィンドウなしのアクティブ化**] を選択した場合、この機能は使用できません。 詳細については、「クリッピングを行っていない[デバイスコンテキストの使用](../../mfc/using-an-unclipped-device-context.md)」を参照してください。

- **ちらつきなしのアクティベーション**

   コントロールのアクティブ状態と非アクティブ状態の間で発生する描画操作と、それに伴う視覚ちらつきを排除します。 [**ウィンドウなしのアクティブ化**] を選択した場合、この機能は使用できません。 このオプションを設定すると、 `noFlickerActivate` フラグは、 [COleControl:: getcontrolflags](../../mfc/reference/colecontrol-class.md#getcontrolflags)によって返されるフラグの1つになります。 詳細については、「[ちらつきなしのアクティベーションの提供](../../mfc/providing-flicker-free-activation.md)」を参照してください。

- **[オブジェクトの挿入] ダイアログで使用可能**

   有効化されたコンテナーの [**オブジェクトの挿入**] ダイアログボックスでコントロールを使用できるように指定します。 このオプションを選択すると、 `afxRegInsertable` フラグはによって返されるフラグの1つに `AfxOleRegisterControlClass` なります。 [オブジェクトの**挿入**] ダイアログボックスを使用すると、新しく作成されたオブジェクトまたは既存のオブジェクトを複合ドキュメントに挿入できます。

- **非アクティブ時のマウスポインター通知**

   コントロールがアクティブかどうかにかかわらず、コントロールがマウスポインターの通知を処理できるようにします。 このオプションを選択すると、 `pointerInactive` フラグは、 [COleControl:: getcontrolflags](../../mfc/reference/colecontrol-class.md#getcontrolflags)によって返されるフラグの1つになります。 このオプションの使用方法の詳細については、「[非アクティブな状態でのマウス操作の提供](../../mfc/providing-mouse-interaction-while-inactive.md)」を参照してください。

- **単純なフレームコントロールとして機能します**

   コントロールが、コントロールの OLEMISC_SIMPLEFRAME ビットを設定することによって、他のコントロールのコンテナーであることを指定します。 詳細については、「[単純なフレームサイトコンテインメント](/windows/win32/com/simple-frame-site-containment)」を参照してください。

- **プロパティを非同期に読み込みます。**

   以前の非同期データのリセットを有効にし、コントロールの非同期プロパティの新しい読み込みを開始します。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロールウィザード](../../mfc/reference/mfc-activex-control-wizard.md)<br/>
[[アプリケーションの設定] (MFC ActiveX コントロールウィザード)](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)<br/>
[[コントロール名] (MFC ActiveX コントロールウィザード)](../../mfc/reference/control-names-mfc-activex-control-wizard.md)
