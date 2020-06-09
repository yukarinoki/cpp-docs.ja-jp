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
ms.openlocfilehash: bf30f1b0aa83ef002337b76601f04c7103963441
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620743"
---
# <a name="class-library-overview"></a>クラス ライブラリの概要

この概要では、MFC (Microsoft Foundation Class) ライブラリ Version 9.0 のクラスを分類し、説明します。 MFC のクラスは、全体として、Windows API 用に記述されたアプリケーションのフレームワークであるアプリケーション フレームワークを構成します。 プログラミング タスクは、アプリケーション固有のコードを入力することです。

ここでは、ライブラリのクラスを次のカテゴリで表します。

- [ルート クラス: CObject](root-class-cobject.md)

- [MFC アプリケーション アーキテクチャ クラス](mfc-application-architecture-classes.md)

  - [アプリケーションおよびスレッド サポート クラス](application-and-thread-support-classes.md)

  - [コマンド ルーティング クラス](command-routing-classes.md)

  - [ドキュメントクラス](document-classes.md)

  - [ビュークラス (アーキテクチャ)](view-classes-architecture.md)

  - [フレーム ウィンドウ クラス (アーキテクチャ)](frame-window-classes-architecture.md)

  - [ドキュメントテンプレートクラス](document-template-classes.md)

- [ウィンドウ、ダイアログ、およびコントロールクラス](window-dialog-and-control-classes.md)

  - [フレームウィンドウクラス (Windows)](frame-window-classes-windows.md)

  - [ビュークラス (Windows)](view-classes-windows.md)

  - [ダイアログ ボックス クラス](dialog-box-classes.md)

  - [コントロール クラス](control-classes.md)

  - [コントロールバークラス](control-bar-classes.md)

- [描画および印刷クラス](drawing-and-printing-classes.md)

  - [出力 (デバイス コンテキスト) クラス](output-device-context-classes.md)

  - [描画ツールクラス](drawing-tool-classes.md)

- [単純データ型クラス](simple-data-type-classes.md)

- [配列、リスト、およびマップクラス](array-list-and-map-classes.md)

  - [配列、リスト、マップのテンプレート クラス](template-classes-for-arrays-lists-and-maps.md)

  - [すぐに使用できる配列クラス](ready-to-use-array-classes.md)

  - [すぐに使用できるリストクラス](ready-to-use-list-classes.md)

  - [すぐに使用できるマップクラス](ready-to-use-map-classes.md)

- [ファイルクラスとデータベースクラス](file-and-database-classes.md)

  - [ファイル I/O クラス](file-i-o-classes.md)

  - [DAO クラス](dao-classes.md)

  - [ODBC クラス](odbc-classes.md)

  - [OLE DB クラス](ole-db-classes.md)

- [インターネットおよびネットワーククラス](internet-and-networking-classes.md)

  - [Windows Sockets クラス](windows-sockets-classes.md)

  - [Win32 インターネット クラス](win32-internet-classes.md)

- [OLE クラス](ole-classes.md)

  - [OLE コンテナー クラス](ole-container-classes.md)

  - [OLE サーバー クラス](ole-server-classes.md)

  - [OLE ドラッグアンドドロップおよびデータ転送クラス](ole-drag-and-drop-and-data-transfer-classes.md)

  - [OLE コモン ダイアログ クラス](ole-common-dialog-classes.md)

  - [OLE オートメーションクラス](ole-automation-classes.md)

  - [OLE コントロール クラス](ole-control-classes.md)

  - [アクティブドキュメントクラス](active-document-classes.md)

  - [OLE 関連クラス](ole-related-classes.md)

- [デバッグおよび例外クラス](debugging-and-exception-classes.md)

  - [デバッグサポートクラス](debugging-support-classes.md)

  - [例外クラス](exception-classes.md)

「[一般的なクラスのデザインの考え方](general-class-design-philosophy.md)」では、MFC ライブラリの設計方法について説明します。

フレームワークの概要については、「 [Windows 用のアプリケーションを記述するためのクラスの使用](using-the-classes-to-write-applications-for-windows.md)」を参照してください。 上記のクラスの一部は、フレームワークの外部で使用できる汎用クラスであり、コレクション、例外、ファイル、文字列などの便利な抽象化を提供します。

クラスの継承を表示するには、[クラス階層図](hierarchy-chart.md)を使用します。

この概要で示されているクラスに加えて、MFC ライブラリには多くのグローバル関数、グローバル変数、およびマクロが含まれています。 これらの概要と詳細な一覧については、「mfc[マクロとグローバル](reference/mfc-macros-and-globals.md)」を参照してください。これは、mfc クラスのアルファベット順のリファレンスに従います。

## <a name="see-also"></a>関連項目

[MFC デスクトップ アプリケーション](mfc-desktop-applications.md)
