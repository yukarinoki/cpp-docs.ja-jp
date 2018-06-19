---
title: 一般的なウィンドウ作成順序 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- sequence [MFC], window creation
- frame windows [MFC], creating
- windows [MFC], creating
- sequence [MFC]
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 75a9c6ecf6516adceda845dadd4f0313ae605f0a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346517"
---
# <a name="general-window-creation-sequence"></a>一般的なウィンドウ作成順序
フレームワークがで説明したものと同じプロセスよりを使用して子などの独自のウィンドウのウィンドウを作成するときに[ドキュメント/ビューの作成](../mfc/document-view-creation.md)です。  
  
 MFC を使用して提供されているすべてのウィンドウ クラス[2 段階の構築](../mfc/one-stage-and-two-stage-construction-of-objects.md)です。 つまり、C++ の呼び出し中に**新しい**演算子、コンス トラクターを割り当てますと C++ オブジェクトを初期化しますが、対応する Windows のウィンドウは作成されません。 呼び出すことによって後で実行されるが、[作成](../mfc/reference/cwnd-class.md#create)ウィンドウ オブジェクトのメンバー関数。  
  
 **作成**メンバー関数では、Windows の期間を格納およびその`HWND`C++ オブジェクトのパブリック データ メンバーに[m_hWnd](../mfc/reference/cwnd-class.md#m_hwnd)です。 **作成**な作成パラメーター経由で完全な柔軟性を提供します。 呼び出しの前に**作成**、グローバル関数でウィンドウ クラスを登録することがあります[AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass)フレームのアイコンとクラスのスタイルを設定するためにします。  
  
 フレーム ウィンドウを使用できます、 [LoadFrame](../mfc/reference/cframewnd-class.md#loadframe)メンバー関数の代わりに**作成**です。 `LoadFrame` 以下のパラメーターを使用して Windows のウィンドウになります。 フレームのキャプション、アイコン、アクセラレータ テーブル、およびメニューなどのリソースから多くの既定値を取得します。  
  
> [!NOTE]
>  アイコン、アクセラレータ テーブル、およびメニュー リソースが必要で共通のリソース ID など**IDR_MAINFRAME**、LoadFrame によって読み込まれることにします。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [ウィンドウ オブジェクト](../mfc/window-objects.md)  
  
-   [ウィンドウ「クラス」の登録](../mfc/registering-window-classes.md)  
  
-   [ウィンドウ オブジェクトの破棄](../mfc/destroying-window-objects.md)  
  
-   [ドキュメント フレーム ウィンドウの作成](../mfc/creating-document-frame-windows.md)  
  
## <a name="see-also"></a>関連項目  
 [ウィンドウの作成](../mfc/creating-windows.md)

