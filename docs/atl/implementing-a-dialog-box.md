---
title: ダイアログ ボックスを実装する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CSimpleDialog class, implementing dialog boxes in ATL
- dialog boxes, ATL
- CAxDialogImpl class, implementing dialog boxes in ATL
- ATL, dialog boxes
ms.assetid: 478525f2-aa6a-435a-b162-68fc8aa98a8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 672696027a43cd5a50e2ad630824d305f7ca4b68
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32355853"
---
# <a name="implementing-a-dialog-box"></a>ダイアログ ボックスの実装
ATL プロジェクトに、ダイアログ ボックスを追加する 2 つの方法があります。 ATL ダイアログ ウィザードを使用するか、手動で追加します。  
  
## <a name="adding-a-dialog-box-with-the-atl-dialog-wizard"></a>ATL ダイアログ ウィザードとダイアログ ボックスの追加  
 [クラスの追加 ダイアログ ボックス](../ide/add-class-dialog-box.md)、ATL プロジェクトに、ダイアログ ボックスを追加する、ATL ダイアログ オブジェクトを選択します。 必要に応じて ATL ダイアログ ウィザードに入力し、をクリックして**完了**です。 派生したクラスが追加されます[CAxDialogImpl](../atl/reference/caxdialogimpl-class.md)をプロジェクトにします。 リソース ビューを開き、**ビュー** ] メニューの [、ダイアログを見つけて、ダブルクリックして、リソース エディターで開きます。  
  
> [!NOTE]
>  ダイアログ ボックスはから派生している場合`CAxDialogImpl`両方 ActiveX をホストできる、および Windows を制御します。 使用する場合は、ダイアログ ボックス クラスでは、ActiveX コントロール サポートのオーバーヘッドをしたくない、 [CSimpleDialog](../atl/reference/csimpledialog-class.md)または[CDialogImpl](../atl/reference/cdialogimpl-class.md)代わりにします。  
  
 メッセージおよびイベント ハンドラーは、クラス ビューからダイアログ クラスに追加できます。 詳細については、次を参照してください。 [ATL メッセージ ハンドラーを追加する](../atl/adding-an-atl-message-handler.md)です。  
  
## <a name="adding-a-dialog-box-manually"></a>ダイアログ ボックスを手動で追加します。  
 ダイアログ ボックスの実装は、ウィンドウの実装に似ています。 いずれかから、クラスを派生[CAxDialogImpl](../atl/reference/caxdialogimpl-class.md)、 [CDialogImpl](../atl/reference/cdialogimpl-class.md)、または[CSimpleDialog](../atl/reference/csimpledialog-class.md)を宣言し、[メッセージ マップ](../atl/message-maps-atl.md)メッセージを処理します。 ただし、派生クラスでダイアログ テンプレート リソース ID を指定することも必要があります。 クラスと呼ばれるデータ メンバーを含める必要があります`IDD`この値を保持します。  
  
> [!NOTE]
>  ATL ダイアログ ウィザードを使用してダイアログ ボックスを作成すると、ウィザードは自動的に追加、`IDD`メンバーとして、`enum`型です。  
  
 `CDialogImpl` 使用すると、モーダルまたはモードレス ダイアログ ボックスの Windows コントロールをホストしている実装できます。 `CAxDialogImpl` 使用すると、モーダルまたはモードレス ダイアログ ボックス コントロールの ActiveX や Windows の両方をホストする実装できます。  
  
 モーダル ダイアログ ボックスを作成するには、インスタンスを作成、 `CDialogImpl`-派生 (または`CAxDialogImpl`-派生) クラスを呼び出す、 [DoModal](../atl/reference/cdialogimpl-class.md#domodal)メソッドです。 モーダル ダイアログ ボックスを閉じるを呼び出して、 [EndDialog](../atl/reference/cdialogimpl-class.md#enddialog)メッセージ ハンドラーからメソッドです。 モードレス ダイアログ ボックスを作成するには、[作成](../atl/reference/cdialogimpl-class.md#create)メソッドの代わりに`DoModal`です。 モードレス ダイアログ ボックスを破棄するには、呼び出す[DestroyWindow](../atl/reference/cdialogimpl-class.md#destroywindow)です。  
  
 自動的に行われるイベントをシンク[CAxDialogImpl](../atl/reference/caxdialogimpl-class.md)です。 内のハンドラーのように、ダイアログ ボックスのメッセージ ハンドラーを実装する`CWindowImpl`-クラスを派生します。 メッセージに固有の戻り値がある場合を返すように、`LRESULT`です。 返された`LRESULT`Windows ダイアログ マネージャーによって正しく処理するための値が ATL によってマップされます。 詳細については、ソース コードを参照してください[CDialogImplBaseT::DialogProc](../atl/reference/cdialogimpl-class.md#dialogproc) atlwin.h 内です。  
  
## <a name="example"></a>例  
 次のクラスには、ダイアログ ボックスを実装します。  
  
 [!code-cpp[NVC_ATL_Windowing#66](../atl/codesnippet/cpp/implementing-a-dialog-box_1.h)]  
  
## <a name="see-also"></a>関連項目  
 [ウィンドウ クラス](../atl/atl-window-classes.md)

