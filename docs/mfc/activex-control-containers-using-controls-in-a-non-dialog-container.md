---
title: 'ActiveX コントロール コンテナー: ダイアログではないコンテナーでコントロールの使用 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Create method [MFC], ActiveX controls
- CreateControl method [MFC]
- ActiveX controls [MFC], creating
- ActiveX control containers [MFC], non-dialog containers
- ActiveX control containers [MFC], inserting controls
ms.assetid: 46f195b0-b8ca-4409-8cca-fbfaf2c9ab9f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 16264e9b072d27349d4375bd7c04d5bbac1be597
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33324903"
---
# <a name="activex-control-containers-using-controls-in-a-non-dialog-container"></a>ActiveX コントロール コンテナー : ダイアログ ベースではないコンテナーでのコントロールの使用
一部の SDI などのアプリケーションまたは MDI アプリケーションでは、アプリケーションのウィンドウにコントロールを埋め込むされます。 **作成**、Visual C によって挿入された、ラッパー クラスのメンバー関数はダイアログ ボックスがなくても、コントロールのインスタンスを動的に作成できます。  
  
 **作成**メンバー関数は、次のパラメーター。  
  
 `lpszWindowName`  
 (存在する場合)、コントロールのテキストまたはキャプション プロパティに表示されるテキストへのポインター。  
  
 `dwStyle`  
 Windows のスタイルです。 完全な一覧についてを参照してください。 [cwnd::createcontrol](../mfc/reference/cwnd-class.md#createcontrol)です。  
  
 `rect`  
 コントロールのサイズと位置を指定します。  
  
 `pParentWnd`  
 コントロールの親ウィンドウを通常を指定します、`CDialog`です。 なければなりません**NULL**です。  
  
 `nID`  
 コントロールの ID を指定し、コントロールを参照するコンテナーで使用できます。  
  
 この関数を使用して動的に ActiveX コントロールを作成する 1 つの例は、SDI アプリケーションのフォーム ビューになります。 内のコントロールのインスタンスを作成し、`WM_CREATE`アプリケーションのハンドラー。  
  
 たとえば、`CMyView`のメイン ビュー クラス`CCirc`はラッパー クラスと可変範囲H はヘッダー (です。H) ファイルのラッパー クラスです。  
  
 4 つの手順は、この機能を実装します。  
  
### <a name="to-dynamically-create-an-activex-control-in-a-non-dialog-window"></a>非ダイアログ ウィンドウで、ActiveX コントロールを動的に作成するには  
  
1.  可変範囲を挿入します。H CMYVIEW にします。H、直前に、`CMyView`クラス定義。  
  
     [!code-cpp[NVC_MFC_AxCont#12](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_1.h)]  
  
2.  メンバー変数を追加 (型の`CCirc`) の保護されたセクションに、`CMyView`クラス CMYVIEW に定義します。H:  
  
     [!code-cpp[NVC_MFC_AxCont#13](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_2.h)]  
    [!code-cpp[NVC_MFC_AxCont#14](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_3.h)]  
  
3.  追加、`WM_CREATE`クラスにメッセージ ハンドラー`CMyView`です。  
  
4.  ハンドラー関数に`CMyView::OnCreate`をコントロールの呼び出しを行う`Create`関数を使用して、**この**親ウィンドウとしてのポインター。  
  
     [!code-cpp[NVC_MFC_AxCont#15](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_4.cpp)]  
  
5.  プロジェクトをリビルドします。 Circ コントロールは、アプリケーションのビューが作成されるたびに動的に作成されます。  
  
## <a name="see-also"></a>関連項目  
 [ActiveX コントロール コンテナー](../mfc/activex-control-containers.md)

