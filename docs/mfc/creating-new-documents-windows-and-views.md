---
title: 新しいドキュメント、ウィンドウ、ビューの作成
ms.date: 11/19/2018
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
ms.openlocfilehash: 7a714b5d7ba97c12b7134fa4890bddf5ed095c5b
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620559"
---
# <a name="creating-new-documents-windows-and-views"></a>新しいドキュメント、ウィンドウ、ビューの作成

次の図は、ドキュメント、ビュー、フレームウィンドウの作成プロセスの概要を示しています。 参加しているオブジェクトに焦点を当てたその他の記事では、詳細を説明します。

このプロセスが完了すると、連携するオブジェクトが存在し、相互にポインターが格納されます。 次の図は、オブジェクトが作成される順序を示しています。 図のようなシーケンスに従うことができます。

![ドキュメント作成のシーケンス](../mfc/media/vc387l1.gif "ドキュメント作成のシーケンス") <br/>
ドキュメントの作成過程

![フレーム ウィンドウ作成シーケンス](../mfc/media/vc387l2.png "フレーム ウィンドウ作成シーケンス") <br/>
フレーム ウィンドウの作成過程

![ビュー作成のシーケンス](../mfc/media/vc387l3.gif "ビュー作成のシーケンス") <br/>
ビューの作成過程

フレームワークが新しいドキュメント、ビュー、およびフレームウィンドウオブジェクトを初期化する方法の詳細については、「MFC ライブラリリファレンス」の「クラス[CDocument](reference/cdocument-class.md)、 [CView](reference/cview-class.md)、 [CFrameWnd](reference/cframewnd-class.md)、 [CMDIFrameWnd](reference/cmdiframewnd-class.md)、および[CMDIChildWnd](reference/cmdichildwnd-class.md) 」を参照してください。 また、「 [Technical Note 22](tn022-standard-commands-implementation.md)」も参照してください。このテクニカルノートでは、[**ファイル**] メニューの**新しい**項目と**開い**ている項目について、フレームワークの標準コマンドについて詳しく説明しています。

## <a name="initializing-your-own-additions-to-these-classes"></a><a name="_core_initializing_your_own_additions_to_these_classes"></a>独自の追加をこれらのクラスに初期化する

また、前の図では、メンバー関数をオーバーライドしてアプリケーションのオブジェクトを初期化できる点も提案しています。 ビュークラスでののオーバーライド `OnInitialUpdate` は、ビューを初期化するのに最適な場所です。 この `OnInitialUpdate` 呼び出しは、フレームウィンドウが作成された直後に発生し、フレームウィンドウ内のビューがドキュメントにアタッチされます。 たとえば、ビューが (ではなくから派生した) スクロールビューである場合は、 `CScrollView` `CView` オーバーライドのドキュメントサイズに基づいてビューサイズを設定する必要があり `OnInitialUpdate` ます。 (このプロセスについては、 [CScrollView](reference/cscrollview-class.md)クラスの説明を参照してください。)`CDocument`メンバー関数 `OnNewDocument` をオーバーライドして、 `OnOpenDocument` ドキュメントのアプリケーション固有の初期化を行うことができます。 通常、ドキュメントは2つの方法で作成できるため、どちらもオーバーライドする必要があります。

ほとんどの場合、オーバーライドで基底クラスのバージョンを呼び出す必要があります。 詳細については、MFC ライブラリリファレンスの「 [CDocument](reference/cdocument-class.md)、 [CView](reference/cview-class.md)、 [CFrameWnd](reference/cframewnd-class.md)、および[CWinApp](reference/cwinapp-class.md)クラスの名前付きメンバー関数」を参照してください。

## <a name="see-also"></a>関連項目

[ドキュメントテンプレートとドキュメント/ビュー作成プロセス](document-templates-and-the-document-view-creation-process.md)<br/>
[ドキュメント テンプレートの作成](document-template-creation.md)<br/>
[ドキュメントおよびビューの作成](document-view-creation.md)<br/>
[MFC オブジェクト間の関係](relationships-among-mfc-objects.md)
