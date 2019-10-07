---
title: フレームワーク (MFC)
ms.date: 09/17/2019
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
ms.openlocfilehash: d93d2d50bab4b63258a3e0fe4cd2f24c2fcde4f3
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2019
ms.locfileid: "71095796"
---
# <a name="framework-mfc"></a>フレームワーク (MFC)

MFC (Microsoft Foundation Class) ライブラリフレームワークでの作業は、主にいくつかの主要なクラスといくつC++かのビジュアルツールに基づいています。 Win32 アプリケーションプログラミングインターフェイス (API) の大部分をカプセル化するクラスもあります。 他のクラスは、ドキュメント、ビュー、アプリケーション自体などのアプリケーションの概念をカプセル化します。 その他のユーザーは、OLE 機能、ODBC および DAO データアクセス機能をカプセル化します。  (DAO は Office 2013 でサポートされています。 DAO 3.6 は最終バージョンであり、互換性のために残されているものと見なされます)。

たとえば、Win32's というウィンドウの概念は、MFC クラス`CWnd`によってカプセル化されています。 つまり、というC++ `CWnd`クラスは、Windows ウィンドウを表す`HWND`ハンドルをカプセル化または "ラップ" します。 同様に、 `CDialog`クラスは Win32 のダイアログボックスをカプセル化します。

カプセル化とはC++ 、 `CWnd`たとえば、クラスには型`HWND`のメンバー変数が含まれ、クラスのメンバー関数はをパラメーター `HWND`として受け取る Win32 関数への呼び出しをカプセル化することを意味します。 クラスメンバー関数には、通常、カプセル化する Win32 関数と同じ名前が付けられています。

## <a name="in-this-section"></a>このセクションの内容

[SDI と MDI](../mfc/sdi-and-mdi.md)

[ドキュメント、ビュー、フレームワーク](../mfc/documents-views-and-the-framework.md)

[ウィザードとリソースエディター](../mfc/wizards-and-the-resource-editors.md)

## <a name="in-related-sections"></a>関連セクション

[フレームワークを使ったアプリケーションの作成](../mfc/building-on-the-framework.md)

[フレームワークと記述したコードとの関係](../mfc/how-the-framework-calls-your-code.md)

[CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)

[ドキュメントテンプレートとドキュメント/ビュー作成プロセス](../mfc/document-templates-and-the-document-view-creation-process.md)

[メッセージの処理とマップ](../mfc/message-handling-and-mapping.md)

[Window オブジェクト](../mfc/window-objects.md)

## <a name="see-also"></a>関連項目

[クラスを使用した Windows アプリケーションの作成](../mfc/using-the-classes-to-write-applications-for-windows.md)
