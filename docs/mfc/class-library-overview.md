---
title: クラス ライブラリの概要
ms.date: 09/17/2019
f1_keywords:
- vc.classes.mfc
helpviewer_keywords:
- grouping MFC classes
- MFC, class library
- classes [MFC], MFC
- class libraries, MFC
- class libraries
ms.assetid: 9b0e3152-ac39-4f52-91b4-f20aa3a674aa
ms.openlocfilehash: 9b307c4993a1a7a397741864381c0739a1f4c4ea
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374574"
---
# <a name="class-library-overview"></a>クラス ライブラリの概要

この概要では、MFC (Microsoft Foundation Class) ライブラリ Version 9.0 のクラスを分類し、説明します。 MFC のクラスは、全体として、Windows API 用に記述されたアプリケーションのフレームワークであるアプリケーション フレームワークを構成します。 プログラミング タスクは、アプリケーション固有のコードを入力することです。

ここでは、ライブラリのクラスを次のカテゴリで表します。

- [ルート クラス: CObject](../mfc/root-class-cobject.md)

- [MFC アプリケーション アーキテクチャ クラス](../mfc/mfc-application-architecture-classes.md)

  - [アプリケーションおよびスレッド サポート クラス](../mfc/application-and-thread-support-classes.md)

  - [コマンド ルーティング クラス](../mfc/command-routing-classes.md)

  - [ドキュメント クラス](../mfc/document-classes.md)

  - [クラスの表示 (アーキテクチャ)](../mfc/view-classes-architecture.md)

  - [フレーム ウィンドウ クラス (アーキテクチャ)](../mfc/frame-window-classes-architecture.md)

  - [ドキュメント テンプレート クラス](../mfc/document-template-classes.md)

- [ウィンドウ、ダイアログ、およびコントロールのクラス](../mfc/window-dialog-and-control-classes.md)

  - [フレーム ウィンドウ クラス (ウィンドウ)](../mfc/frame-window-classes-windows.md)

  - [クラスの表示 (ウィンドウ)](../mfc/view-classes-windows.md)

  - [ダイアログ ボックス クラス](../mfc/dialog-box-classes.md)

  - [コントロール クラス](../mfc/control-classes.md)

  - [コントロール バー クラス](../mfc/control-bar-classes.md)

- [描画クラスと印刷クラス](../mfc/drawing-and-printing-classes.md)

  - [出力 (デバイス コンテキスト) クラス](../mfc/output-device-context-classes.md)

  - [描画ツール クラス](../mfc/drawing-tool-classes.md)

- [単純データ型クラス](../mfc/simple-data-type-classes.md)

- [配列、リスト、およびマップ クラス](../mfc/array-list-and-map-classes.md)

  - [配列、リスト、マップのテンプレート クラス](../mfc/template-classes-for-arrays-lists-and-maps.md)

  - [すぐに使用できる配列クラス](../mfc/ready-to-use-array-classes.md)

  - [すぐに使用できるリスト クラス](../mfc/ready-to-use-list-classes.md)

  - [すぐに使用できるマップ クラス](../mfc/ready-to-use-map-classes.md)

- [ファイルとデータベースのクラス](../mfc/file-and-database-classes.md)

  - [ファイル I/O クラス](../mfc/file-i-o-classes.md)

  - [DAO クラス](../mfc/dao-classes.md)

  - [ODBC クラス](../mfc/odbc-classes.md)

  - [OLE DB クラス](../mfc/ole-db-classes.md)

- [インターネットとネットワークのクラス](../mfc/internet-and-networking-classes.md)

  - [Windows Sockets クラス](../mfc/windows-sockets-classes.md)

  - [Win32 インターネット クラス](../mfc/win32-internet-classes.md)

- [OLE クラス](../mfc/ole-classes.md)

  - [OLE コンテナー クラス](../mfc/ole-container-classes.md)

  - [OLE サーバー クラス](../mfc/ole-server-classes.md)

  - [OLE ドラッグ アンド ドロップおよびデータ転送クラス](../mfc/ole-drag-and-drop-and-data-transfer-classes.md)

  - [OLE コモン ダイアログ クラス](../mfc/ole-common-dialog-classes.md)

  - [OLE オートメーション クラス](../mfc/ole-automation-classes.md)

  - [OLE コントロール クラス](../mfc/ole-control-classes.md)

  - [アクティブ ドキュメント クラス](../mfc/active-document-classes.md)

  - [OLE 関連クラス](../mfc/ole-related-classes.md)

- [デバッグ クラスと例外クラス](../mfc/debugging-and-exception-classes.md)

  - [サポート クラスのデバッグ](../mfc/debugging-support-classes.md)

  - [例外クラス](../mfc/exception-classes.md)

「[クラスの一般設計哲学](../mfc/general-class-design-philosophy.md)」では、MFC ライブラリがどのように設計されたかについて説明します。

フレームワークの概要については、「[クラスを使用して Windows 用アプリケーションを記述する 」](../mfc/using-the-classes-to-write-applications-for-windows.md)を参照してください。 上記のクラスの一部は、フレームワークの外部で使用できる汎用クラスであり、コレクション、例外、ファイル、文字列などの便利な抽象化を提供します。

クラスの継承を確認するには、[クラス階層図](../mfc/hierarchy-chart.md)を使用します。

この概要で示されているクラスに加えて、MFC ライブラリには多くのグローバル関数、グローバル変数、およびマクロが含まれています。 MFC のクラスのアルファベット順のリファレンスに続く MFC[マクロとグローバル](../mfc/reference/mfc-macros-and-globals.md)トピックに、これらの概要と詳細な一覧があります。

## <a name="see-also"></a>関連項目

[MFC デスクトップ アプリケーション](../mfc/mfc-desktop-applications.md)
