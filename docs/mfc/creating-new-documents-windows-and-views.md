---
title: 新しいドキュメント、Windows、およびビューを作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MDI [MFC], creating windows
- window objects [MFC], creating
- objects [MFC], creating document objects
- MFC default objects
- frame windows [MFC], creating
- windows [MFC], MDI
- MFC, documents
- view objects [MFC], creating
- windows [MFC], creating
- overriding, default view behavior
- views [MFC], initializing
- customizing MFC default objects
- MFC, frame windows
- MFC, views
- MDI [MFC], frame windows
- child windows [MFC], creating MDI
- view objects [MFC]
- document objects [MFC], creating
- MFC default objects [MFC], customizing
- views [MFC], overriding default behavior
- initializing views [MFC]
ms.assetid: 88aa1f5f-2078-4603-b16b-a2b4c7b4a2a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89d929f4d7419e027a1018c4b0b33a4e42416613
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="creating-new-documents-windows-and-views"></a>新しいドキュメント、ウィンドウ、ビューの作成
次の図は、ドキュメント、ビュー、およびフレーム ウィンドウの作成プロセスの概要を説明します。 参加しているオブジェクトに集中する他の記事の詳細ではさらに説明します。  
  
 このプロセスの完了は、協調動作するオブジェクトが存在し、相互にポインターを格納します。 次の図は、オブジェクトが作成された順序を示しています。 シーケンス図に従うことができます。  
  
 ![ドキュメントを作成するためのシーケンス](../mfc/media/vc387l1.gif "vc387l1")  
ドキュメントの作成過程  
  
 ![フレーム ウィンドウ作成順序](../mfc/media/vc387l2.png "vc387l2")  
フレーム ウィンドウの作成過程  
  
 ![ビューを作成するためのシーケンス](../mfc/media/vc387l3.gif "vc387l3")  
ビューの作成過程  
  
 フレームワークが新しいドキュメント、ビュー、およびフレーム ウィンドウ オブジェクトを初期化する方法については、クラスを参照してください[CDocument](../mfc/reference/cdocument-class.md)、 [CView](../mfc/reference/cview-class.md)、 [CFrameWnd](../mfc/reference/cframewnd-class.md)、 [。CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)、および[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) MFC ライブラリ リファレンスです。 参照してください[テクニカル ノート 22:](../mfc/tn022-standard-commands-implementation.md)、そのディスカッションのフレームワークの標準コマンドの下でさらに作成および初期化プロセスについて説明しています、`New`と**開く**上の項目、**ファイル**メニュー。  
  
##  <a name="_core_initializing_your_own_additions_to_these_classes"></a> これらのクラスに、独自の追加の初期化  
 上記の図では、するには、アプリケーションのオブジェクトを初期化するためにメンバー関数をオーバーライドできますポイントも提示されます。 オーバーライド`OnInitialUpdate`ビュー クラスは、ビューを初期化するために最適な場所です。 `OnInitialUpdate`呼び出しフレーム ウィンドウが作成され、フレーム ウィンドウ内のビューがその文書に添付された直後後に発生します。 たとえば、ビューがスクロール可能なビュー (から派生した`CScrollView`なく`CView`) のドキュメント サイズに基づくビューのサイズを設定する必要があります、`OnInitialUpdate`をオーバーライドします。 (このプロセスは、クラスの説明に記載されて[CScrollView](../mfc/reference/cscrollview-class.md))。オーバーライドすることができます、 **CDocument**メンバー関数`OnNewDocument`と`OnOpenDocument`をドキュメントのアプリケーション固有の初期化を提供します。 通常、2 つの方法でドキュメントを作成することができますので両方をオーバーライドする必要があります。  
  
 ほとんどの場合、オーバーライドは基底クラスのバージョンを呼び出す必要があります。 詳細については、クラスの名前付きのメンバー関数を参照してください[CDocument](../mfc/reference/cdocument-class.md)、 [CView](../mfc/reference/cview-class.md)、 [CFrameWnd](../mfc/reference/cframewnd-class.md)、および[CWinApp](../mfc/reference/cwinapp-class.md) 、MFC で。ライブラリの参照。  
  
## <a name="see-also"></a>関連項目  
 [ドキュメント テンプレートとドキュメント/ビューの作成手順](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [ドキュメント テンプレートの作成](../mfc/document-template-creation.md)   
 [ドキュメント/ビューの作成](../mfc/document-view-creation.md)   
 [各種 MFC オブジェクト間の関係](../mfc/relationships-among-mfc-objects.md)

