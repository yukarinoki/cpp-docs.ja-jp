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
ms.openlocfilehash: aa1c58b02df92d79ca9915032b97fb5c0e2eaffc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371664"
---
# <a name="creating-new-documents-windows-and-views"></a>新しいドキュメント、ウィンドウ、ビューの作成

次の図は、ドキュメント、ビュー、およびフレーム ウィンドウの作成プロセスの概要を示しています。 参加オブジェクトに焦点を当てた他の記事では、さらに詳細を説明します。

このプロセスが完了すると、連携するオブジェクトが存在し、相互にポインターを格納します。 次の図は、オブジェクトが作成される順序を示しています。 図から図までシーケンスをたどることができます。

![ドキュメント作成のシーケンス](../mfc/media/vc387l1.gif "ドキュメント作成のシーケンス") <br/>
ドキュメントの作成過程

![フレーム ウィンドウ作成シーケンス](../mfc/media/vc387l2.png "フレーム ウィンドウ作成シーケンス") <br/>
フレーム ウィンドウの作成過程

![ビュー作成のシーケンス](../mfc/media/vc387l3.gif "ビュー作成のシーケンス") <br/>
ビューの作成過程

フレームワークが新しいドキュメント、ビュー、およびフレーム ウィンドウ オブジェクトを初期化する方法については、MFC ライブラリ リファレンスのクラス[CDocument、CView](../mfc/reference/cdocument-class.md) [、CFrameWnd](../mfc/reference/cframewnd-class.md) [、CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)、および[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)を参照してください。 [CView](../mfc/reference/cview-class.md) また、「ファイル」メニューの **「新規作成**」および「**開く**」項目に対するフレームワークの標準コマンドの説明のもと、作成と初期化のプロセスについて詳しく説明する[「テクニカルノート 22」](../mfc/tn022-standard-commands-implementation.md)を**参照**してください。

## <a name="initializing-your-own-additions-to-these-classes"></a><a name="_core_initializing_your_own_additions_to_these_classes"></a>これらのクラスに対する独自の追加の初期化

上の図は、アプリケーションのオブジェクトを初期化するためにメンバー関数をオーバーライドできるポイントも示しています。 ビュー クラス`OnInitialUpdate`での オーバーライドは、ビューを初期化するのに最適な場所です。 呼`OnInitialUpdate`び出しは、フレーム ウィンドウが作成され、フレーム ウィンドウ内のビューがそのドキュメントにアタッチされた直後に発生します。 たとえば、ビューがスクロール ビュー (`CScrollView`から派生したもの)`CView`の場合は、オーバーライドのドキュメント サイズに基づいてビュー サイズ`OnInitialUpdate`を設定する必要があります。 (このプロセスはクラス[CScrollView](../mfc/reference/cscrollview-class.md)の説明で説明されています。メンバー関数`CDocument``OnNewDocument`をオーバーライドして、`OnOpenDocument`アプリケーション固有のドキュメントの初期化を行うことができます。 通常、ドキュメントは 2 つの方法で作成できるため、両方をオーバーライドする必要があります。

ほとんどの場合、オーバーライドは基本クラスバージョンを呼び出す必要があります。 詳細については、MFC ライブラリ リファレンスで[CDocument、CView](../mfc/reference/cdocument-class.md) [、CFrameWnd](../mfc/reference/cframewnd-class.md)、および[CWinApp](../mfc/reference/cwinapp-class.md)クラスの名前付きメンバー関数を参照してください。 [CView](../mfc/reference/cview-class.md)

## <a name="see-also"></a>関連項目

[ドキュメント テンプレートとドキュメント/ビュー作成プロセス](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[ドキュメント テンプレートの作成](../mfc/document-template-creation.md)<br/>
[ドキュメントおよびビューの作成](../mfc/document-view-creation.md)<br/>
[MFC オブジェクト間の関係](../mfc/relationships-among-mfc-objects.md)
