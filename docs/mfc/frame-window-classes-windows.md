---
title: フレーム ウィンドウ クラス (Windows)
ms.date: 11/04/2016
f1_keywords:
- vc.classes.frame
helpviewer_keywords:
- frame window classes [MFC], reference
ms.assetid: 6342ec5f-f922-4da8-a78e-2f5f994c7142
ms.openlocfilehash: 1c0a1e1e93433e0fbe07c11eb350216173e74d84
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625852"
---
# <a name="frame-window-classes-windows"></a>フレーム ウィンドウ クラス (Windows)

フレームウィンドウとは、アプリケーションまたはアプリケーションの一部をフレームにするウィンドウのことです。 通常、フレームウィンドウには、ビュー、ツールバー、ステータスバーなど、他のウィンドウが含まれています。 の場合 `CMDIFrameWnd` 、オブジェクトに間接的にオブジェクトが含まれている可能性があり `CMDIChildWnd` ます。

[CFrameWnd](reference/cframewnd-class.md)<br/>
SDI アプリケーションのメインフレームウィンドウの基本クラス。 他のすべてのフレームウィンドウクラスの基本クラスでもあります。

[CMDIFrameWnd](reference/cmdiframewnd-class.md)<br/>
MDI アプリケーションのメインフレームウィンドウの基本クラス。

[CMDIChildWnd](reference/cmdichildwnd-class.md)<br/>
MDI アプリケーションのドキュメントフレームウィンドウの基本クラス。

[CMiniFrameWnd](reference/cminiframewnd-class.md)<br/>
通常、フローティングツールバーの周りに表示されるハーフハイトフレームウィンドウです。

[クラスからではなく、](reference/coleipframewnd-class.md)<br/>
サーバードキュメントをその場で編集しているときに、ビューのフレームウィンドウを提供します。

## <a name="related-class"></a>関連クラス

クラスに `CMenu` は、アプリケーションのメニューにアクセスするためのインターフェイスが用意されています。 実行時にメニューを動的に操作する場合に便利です。たとえば、コンテキストに従ってメニュー項目を追加または削除する場合などです。 多くの場合、メニューはフレームウィンドウで使用されますが、ダイアログボックスや他の非子ウィンドウで使用することもできます。

[CMenu](reference/cmenu-class.md)<br/>
`HMENU`アプリケーションのメニューバーとポップアップメニューへのハンドルをカプセル化します。

## <a name="see-also"></a>関連項目

[クラスの概要](class-library-overview.md)
