---
description: '詳細情報: クラスを使用して Windows 用のアプリケーションを作成する'
title: クラスを使用した Windows アプリケーションの作成
ms.date: 11/04/2016
helpviewer_keywords:
- Windows applications [MFC], MFC application framework
- MFC, application development
- applications [OLE], MFC application framework
- MFC ActiveX controls [MFC], creating
- OLE applications [MFC], MFC application framework
- database applications [MFC], creating
ms.assetid: 73f63470-857d-43dd-9a54-b38b7be0f1b7
ms.openlocfilehash: b94155b565872b614efa291699cecbaf4770fdaa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322713"
---
# <a name="using-the-classes-to-write-applications-for-windows"></a>クラスを使用した Windows アプリケーションの作成

Microsoft Foundation Class (MFC) ライブラリのクラスは、Windows オペレーティングシステム用のアプリケーションをビルドする "アプリケーションフレームワーク" を構成します。 非常に一般的なレベルでは、フレームワークはアプリケーションのスケルトンを定義し、スケルトンに配置できる標準のユーザーインターフェイスの実装を提供します。 プログラマとしての仕事は、アプリケーションに固有のものであるスケルトンの残りの部分を入力することです。 MFC アプリケーションウィザードを使用して、非常に完全なスターターアプリケーションのファイルを作成することにより、先頭を取得できます。 Microsoft Visual C++ リソースエディターを使用して、ユーザーインターフェイス要素を視覚的にデザインしたり、これらの要素をコードに接続するためのコマンドをクラスビューしたり、アプリケーション固有のロジックを実装するためのクラスライブラリを作成したりします。

MFC フレームワークのバージョン3.0 以降は、Microsoft Windows 95 以降および Windows NT バージョン3.51 以降を含む Win32 プラットフォームのプログラミングをサポートしています。 MFC Win32 サポートにはマルチスレッドが含まれます。 16ビットプログラミングを行う必要がある場合は、バージョン 1.5 *x* を使用します。

この記事の記事では、アプリケーションフレームワークの概要について説明します。 また、アプリケーションを構成する主要なオブジェクトとその作成方法についても説明します。 これらの記事では、次のトピックについて説明します。

- [フレームワーク](../mfc/framework-mfc.md)。

- 「 [フレームワークでの構築](../mfc/building-on-the-framework.md)」で説明されているように、フレームワークとコードの間の労力を分担します。

- アプリケーションクラス。アプリケーションレベル[の](../mfc/cwinapp-the-application-class.md)機能をカプセル化します。

- [ドキュメントテンプレート](../mfc/document-templates-and-the-document-view-creation-process.md)で、ドキュメントとそれに関連付けられているビューおよびフレームウィンドウを作成および管理する方法を説明します。

- すべてのウィンドウのルート基本クラスである [CWnd](../mfc/window-objects.md)クラス。

- ペンやブラシなどの[グラフィックオブジェクト](../mfc/graphic-objects.md)。

フレームワークのその他の部分は次のとおりです。

- [ウィンドウオブジェクト: 概要](../mfc/window-objects.md)

- [メッセージの処理とマップ](../mfc/message-handling-and-mapping.md)

- [CObject (MFC のルート基底クラス)](../mfc/using-cobject.md)

- [ドキュメント/ビューアーキテクチャ](../mfc/document-view-architecture.md)

- [ダイアログボックス](../mfc/dialog-boxes.md)

- [コントロール](../mfc/controls-mfc.md)

- [コントロールバー](../mfc/control-bars.md)

- [OLE●ole○](../mfc/ole-in-mfc.md)

- [メモリ管理](../mfc/memory-management.md)

   MFC では、Windows オペレーティングシステム用のアプリケーションを作成することができるだけでなく、OLE リンクおよび埋め込みテクノロジを使用するアプリケーションを簡単に記述できるようになりました。 アプリケーションを OLE ビジュアル編集コンテナー、OLE ビジュアル編集サーバー、またはその両方にすることができます。また、他のアプリケーションがアプリケーションのオブジェクトを使用できるように自動化を追加したり、リモートでドライブを使用したりすることもできます。

- [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)

   OLE コントロール開発キット (CDK) がフレームワークと完全に統合されました。 この記事ファミリでは、MFC を使用した ActiveX コントロール開発の概要を説明します。 (ActiveX コントロールは、以前は OLE コントロールと呼ばれていました)。

- [データベースプログラミング](../data/data-access-programming-mfc-atl.md)

   MFC には、データアクセスアプリケーションの作成を簡略化する2セットのデータベースクラスも用意されています。 ODBC データベースクラスを使用すると、Open Database Connectivity (ODBC) ドライバーを使用してデータベースに接続し、テーブルからレコードを選択して、レコード情報を画面上の形式で表示できます。 データアクセスオブジェクト (DAO) クラスを使用すると、Microsoft Jet データベースエンジンまたは ODBC データソースを含む外部 (Jet 以外の) データソースを使用してデータベースを操作できます。

   さらに、MFC は、Unicode およびマルチバイト文字セット (MBCS) を使用するアプリケーション (特に2バイト文字セット (DBCS)) を記述するために完全に有効になっています。

MFC ドキュメントの一般的なガイドについては、「 [mfc の一般的なトピック](../mfc/general-mfc-topics.md)」を参照してください。

## <a name="see-also"></a>関連項目

[MFC の一般的なトピック](../mfc/general-mfc-topics.md)
