---
title: MFC ActiveX コントロール ウィザード、設定を制御 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.ctl.settings
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX Control Wizard, control settings
ms.assetid: 2ccaa4fc-0d52-413e-afa3-ecd474c3f6f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2161cea739d918bc0f5772a6cb08c29082a6e670
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="control-settings-mfc-activex-control-wizard"></a>[コントロールの設定] (MFC ActiveX コントロール ウィザード)
ウィザードのこのページを使用すると、動作を制御する方法を指定できます。 たとえば、標準の Windows のコントロール型に制御の基盤な動作と外観を最適化する、またはコントロールの他のコントロールのコンテナーとして機能するかを示すできます。  
  
 このページで、コントロールの効率を最大化するオプションを選択する方法の詳細については、次を参照してください。 [MFC ActiveX コントロール: 最適化](../../mfc/mfc-activex-controls-optimization.md)です。  
  
## <a name="uielement-list"></a>UIElement の一覧  
 **コントロールに基づく作成します。**  
 この一覧には、コントロールを継承元となるコントロールの種類を選択できます。 一覧で利用可能なコントロール クラスのサブセットである`CreateWindowEx`と commctrl.h で指定されているコモン コントロールを追加します。 選択したコントロールのスタイルを決定する、`PreCreateWindow`で機能、 *ProjName*Ctrl.cpp ファイル。 詳細については、次を参照してください。 [MFC ActiveX コントロール: Windows コントロールのサブクラス化](../../mfc/mfc-activex-controls-subclassing-a-windows-control.md)です。  
  
|コントロール|説明|  
|-------------|-----------------|  
|**ボタン**|Windows ボタン コントロール|  
|**コンボ ボックス**|Windows コンボ ボックス コントロール|  
|**編集します。**|Windows のエディット ボックス コントロール|  
|**リスト ボックス**|Windows のリスト ボックス コントロール|  
|**スクロール バー**|Windows のスクロール バー コントロール|  
|**静的**|Windows のスタティック コントロール|  
|**msctls_hotkey32**|ホット キーのコモン コントロール|  
|**msctls_progress32**|プログレス バー コモン コントロール|  
|**msctls_statusbar32**|ステータス バー コモン コントロール|  
|**msctls_trackbar32**|トラック バー コモン コントロール|  
|**msctls_updown32**|スピン ボタン (または上下) コモン コントロール|  
|**SysAnimate32**|アニメーションのコモン コントロール|  
|**SysHeader32**|ヘッダーのコモン コントロール|  
|**SysListView32**|リスト ビューのコモン コントロール|  
|**SysTabControl32**|タブのコモン コントロール|  
|**SysTreeView32**|ツリー ビューのコモン コントロール|  
  
 **表示されている場合にアクティブ化します。**  
 アクセスする場合、コントロールのウィンドウを作成することを指定します。 既定では、**表示時にアクティブ**オプションを選択します。 コンテナーが (たとえば、ユーザーがマウスをクリックする) 必要になるまで、コントロールのアクティブ化を遅延させる場合は、このオプションをオフにします。 この機能がオフの場合、コントロールは発生しません、高価なウィンドウの作成が必要になるまで。 詳細については、次を参照してください。[オプションのオフ、アクティブ化するときに表示されている](../../mfc/turning-off-the-activate-when-visible-option.md)です。  
  
 **実行時に非表示**  
 コントロールは、実行時にユーザー インターフェイスがないことを指定します。 タイマーは、種類のコントロールを非表示にすることがあります。  
  
 **バージョン情報ボックス ダイアログします。**  
 コントロールに標準の Windows があることを示す**に関する** ダイアログ ボックスは、バージョン番号と著作権情報が表示されます。  
  
> [!NOTE]
>  ユーザーがコントロールのヘルプにアクセスする方法は、ヘルプを実装する方法と、コントロールのヘルプを統合、コンテナーを使用したかどうかによって異なります。 のヘルプを統合する方法について、 [MSDN ライブラリ](http://go.microsoft.com/fwlink/p/?linkid=150542)web サイト、「を追加する状況依存のヘルプを MFC ActiveX コントロール」を検索します。  
  
 挿入は、このオプションを選択すると、`AboutBox`プロジェクト コントロール クラスのメソッドを制御 (C*ProjName*Ctrl.cpp) し、プロジェクトのディスパッチ マップにオンを追加します。 既定では、このチェック ボックスはオンになっています。  
  
 **最適化されたコードの描画**  
 コンテナー元の GDI オブジェクトを自動的に復元結局のところ、同じデバイス コンテキストに描画されます、描画されたそのコンテナー コントロールを指定します。 この機能の詳細については、次を参照してください。[コントロールの描画の最適化](../../mfc/optimizing-control-drawing.md)です。  
  
 **ウィンドウなしのアクティベーション**  
 コントロールがないを生成する、ウィンドウがアクティブになることを指定します。 ウィンドウなしのアクティベーションで、四角形以外または透明なコントロールは、およびウィンドウなしのコントロールは、システムのオーバーヘッドが少ないよりをウィンドウを持つコントロールが必要ですが必要です。 クリッピングを行わないデバイス コンテキストまたはちらつきなしのアクティベーションは、ウィンドウなしのコントロールすることはできません。 1996 年以前に作成されたコンテナーは、ウィンドウなしのアクティベーションをサポートしていません。 このオプションを使用する方法の詳細については、次を参照してください。[ウィンドウなしのアクティベーション](../../mfc/providing-windowless-activation.md)です。  
  
 **クリッピングを行わないデバイス コンテキスト**  
 オーバーライド[オン](../../mfc/reference/colecontrol-class.md#getcontrolflags)コントロールのヘッダー (*projname*ctrl.h) への呼び出しを無効にする`IntersectClipRect`によって行われた`COleControl`です。 このオプションを選択すると、小規模のスピードに関する利点を提供します。 選択した場合**ウィンドウなしのアクティベーション**、この機能は使用できません。 詳細については、次を参照してください。[クリッピングを行わないデバイス コンテキストの使用](../../mfc/using-an-unclipped-device-context.md)です。  
  
 **ちらつきなしのアクティベーション**  
 描画操作とコントロールのアクティブおよび非アクティブ状態の間で発生するちらつきを除去します。 選択した場合**ウィンドウなしのアクティベーション**、この機能は使用できません。 このオプションを設定すると、`noFlickerActivate`フラグは、によって返されるフラグのいずれかの[オン](../../mfc/reference/colecontrol-class.md#getcontrolflags)です。 詳細については、次を参照してください。[ちらつきなしのアクティベーション](../../mfc/providing-flicker-free-activation.md)です。  
  
 **[オブジェクトの挿入] ダイアログ ボックス**  
 コントロールがで使用できることを指定します、**オブジェクトの挿入** ダイアログ ボックスの有効なコンテナーです。 このオプションを選択すると、`afxRegInsertable`フラグは、によって返されるフラグのいずれかの`AfxOleRegisterControlClass`します。 使用して、**オブジェクトの挿入**ダイアログ ボックスで、ユーザーは、新しく作成されたが挿入または既存のオブジェクトを複合ドキュメント。  
  
 **非アクティブ時のマウス ポインター通知**  
 コントロールがアクティブかどうかは、マウス ポインターの通知を処理する、コントロールを有効にします。 このオプションを選択すると、`pointerInactive`フラグは、によって返されるフラグのいずれかの[オン](../../mfc/reference/colecontrol-class.md#getcontrolflags)です。 このオプションを使用する方法の詳細については、次を参照してください。[を提供するマウス操作中にアクティブでない](../../mfc/providing-mouse-interaction-while-inactive.md)です。  
  
 **シンプル フレーム コントロールとして機能**  
 指定するコントロールの他のコントロールのコンテナーを設定して、`OLEMISC_SIMPLEFRAME`コントロールのビットです。 詳細については、上、 [MSDN ライブラリ](http://go.microsoft.com/fwlink/p/?linkid=150542)web サイト、「シンプル フレーム サイト含有」を検索します。  
  
 **プロパティを非同期的に読み込みます**  
 以前の非同期データのリセットを有効にし、コントロールの非同期のプロパティの新しい読み込みを開始します。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール ウィザード](../../mfc/reference/mfc-activex-control-wizard.md)   
 [アプリケーションの設定、MFC ActiveX コントロール ウィザード](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)   
 [[コントロール名] (MFC ActiveX コントロール ウィザード)](../../mfc/reference/control-names-mfc-activex-control-wizard.md)

