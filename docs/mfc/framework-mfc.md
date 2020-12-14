---
description: '詳細情報: フレームワーク (MFC)'
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
ms.openlocfilehash: 12e5a28e231dfadec867213ebf1cea6fd6ae7300
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193488"
---
# <a name="framework-mfc"></a>フレームワーク (MFC)

MFC (Microsoft Foundation Class) ライブラリフレームワークでの作業は、主にいくつかの主要なクラスといくつかの Visual C++ ツールに基づいています。 Win32 アプリケーションプログラミングインターフェイス (API) の大部分をカプセル化するクラスもあります。 他のクラスは、ドキュメント、ビュー、アプリケーション自体などのアプリケーションの概念をカプセル化します。 その他のユーザーは、OLE 機能、ODBC および DAO データアクセス機能をカプセル化します。  (DAO は Office 2013 でサポートされています。 DAO 3.6 は最終バージョンであり、互換性のために残されているものと見なされます)。

たとえば、Win32's というウィンドウの概念は、MFC クラスによってカプセル化されてい `CWnd` ます。 つまり、という名前の C++ クラスは、 `CWnd` `HWND` Windows ウィンドウを表すハンドルをカプセル化または "ラップ" します。 同様に、クラスは `CDialog` Win32 のダイアログボックスをカプセル化します。

カプセル化とは、たとえば、C++ クラスには `CWnd` 型のメンバー変数が含まれ、 `HWND` クラスのメンバー関数はを `HWND` パラメーターとして受け取る Win32 関数への呼び出しをカプセル化することを意味します。 クラスメンバー関数には、通常、カプセル化する Win32 関数と同じ名前が付けられています。

## <a name="in-this-section"></a>このセクションの内容

[SDI と MDI](sdi-and-mdi.md)

[ドキュメント、ビュー、フレームワーク](documents-views-and-the-framework.md)

[ウィザードとリソースエディター](wizards-and-the-resource-editors.md)

## <a name="in-related-sections"></a>関連セクション

[フレームワークでのビルド](building-on-the-framework.md)

[フレームワークがコードを呼び出す方法](how-the-framework-calls-your-code.md)

[CWinApp: Application クラス](cwinapp-the-application-class.md)

[ドキュメントテンプレートとドキュメント/ビュー作成プロセス](document-templates-and-the-document-view-creation-process.md)

[メッセージの処理とマッピング](message-handling-and-mapping.md)

[ウィンドウオブジェクト](window-objects.md)

## <a name="see-also"></a>関連項目

[クラスを使用して Windows 用のアプリケーションを作成する](using-the-classes-to-write-applications-for-windows.md)
