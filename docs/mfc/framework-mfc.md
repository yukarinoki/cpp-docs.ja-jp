---
title: フレームワーク (MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- encapsulation [MFC], Win32 API
- MFC, application framework
- wrapper classes [MFC], explained
- Win32 [MFC], API encapsulation by MFC
- application framework [MFC], about MFC application framework
- APIs [MFC], encapsulation by MFC Win32
- encapsulation [MFC]
- Windows API [MFC], encapsulation by MFC
- encapsulated Win32 API [MFC]
ms.assetid: 3be0fec8-9843-4119-ae42-ece993ef500b
ms.openlocfilehash: ff29a867a8351a51ad7f09a5ca31d871fc67bab8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50589307"
---
# <a name="framework-mfc"></a>フレームワーク (MFC)

Microsoft Foundation Class (MFC) ライブラリ、フレームワークを使用する作業は、いくつかの主要なクラスといくつかの Visual C ツールの大部分に基づきます。 いくつかのクラスは、Win32 アプリケーション プログラミング インターフェイス (API) の大部分をカプセル化します。 その他のクラスは、ドキュメント、ビュー、およびアプリケーション自体などのアプリケーションの概念をカプセル化します。 まだ他のユーザー エラーは、OLE の機能とデータ アクセス機能が ODBC と DAO カプセル化します。

ウィンドウの Win32 の概念が MFC クラスによってカプセル化など、`CWnd`します。 つまり、C++ のクラスと呼ばれる`CWnd`をカプセル化または「ラップ」、 `HWND` Windows ウィンドウを表すハンドルです。 同様に、クラス`CDialog`Win32 ダイアログ ボックスをカプセル化します。

カプセル化することで、C++ クラス`CWnd`、たとえば、型のメンバー変数が含まれます`HWND`、クラスのメンバー関数は、Win32 関数への呼び出しをカプセル化し、`HWND`をパラメーターとして。 通常、クラスのメンバー関数には、カプセル化しており、Win32 関数と同じ名前があります。

## <a name="in-this-section"></a>このセクションの内容

[SDI と MDI](../mfc/sdi-and-mdi.md)

[ドキュメント、ビュー、フレームワーク](../mfc/documents-views-and-the-framework.md)

[ウィザードおよびリソース エディター](../mfc/wizards-and-the-resource-editors.md)

## <a name="in-related-sections"></a>関連項目

[フレームワークを使ったアプリケーションの作成](../mfc/building-on-the-framework.md)

[フレームワークと記述したコードとの関係](../mfc/how-the-framework-calls-your-code.md)

[CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)

[ドキュメント テンプレートとドキュメント/ビューの作成手順](../mfc/document-templates-and-the-document-view-creation-process.md)

[メッセージの処理とマップ](../mfc/message-handling-and-mapping.md)

[Window オブジェクト](../mfc/window-objects.md)

## <a name="see-also"></a>関連項目

[クラスを使用した Windows アプリケーションの作成](../mfc/using-the-classes-to-write-applications-for-windows.md)
