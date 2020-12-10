---
title: Microsoft Foundation Classes (MFC) アプリケーションアーキテクチャクラス
description: MFC (Microsoft Foundation Class) ライブラリアプリケーションアーキテクチャクラスの概要について説明します。
ms.date: 12/08/2020
helpviewer_keywords:
- MFC, classes
- MFC, application development
- classes [MFC], MFC
- application architecture classes [MFC]
ms.openlocfilehash: 65aa9707d361c6d014c67c0f9ff1af86e19087de
ms.sourcegitcommit: 754df5278f795f661d4eeb0d4cacc908aa630159
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96933197"
---
# <a name="mfc-application-architecture-classes"></a>MFC アプリケーション アーキテクチャ クラス

このカテゴリの Microsoft Foundation Class ライブラリ (MFC) クラスは、MFC アプリケーションのアーキテクチャに寄与します。 ほとんどのアプリケーションに共通の機能を提供します。 アプリケーション固有の機能を追加するには、フレームワークに入力します。 通常は、アーキテクチャクラスから新しいクラスを派生させ、新しいメンバーを追加するか、既存のメンバー関数をオーバーライドします。

[アプリケーションウィザード](reference/mfc-application-wizard.md) では、アプリケーションフレームワークをさまざまな方法で使用する、複数の種類のアプリケーションが生成されます。 SDI (シングルドキュメントインターフェイス) と MDI (マルチドキュメントインターフェイス) アプリケーションでは、フレームワークのドキュメント/ビュー部分が完全に使用されます。 ダイアログベースのアプリケーション、フォームベースのアプリケーション、Dll など、他の種類のアプリケーションでは、ドキュメント/ビューアーキテクチャの機能の一部のみを使用します。

ドキュメント/ビューアプリケーションには、ドキュメント、ビュー、およびフレームウィンドウの1つ以上のセットが含まれています。 ドキュメントテンプレートオブジェクトは、各ドキュメント/ビュー/フレームセットのクラスを関連付けます。

MFC アプリケーションでは、ドキュメント/ビューアーキテクチャを使用する必要はありませんが、そのためにはさまざまな利点があります。 MFC OLE コンテナーとサーバーのサポートは、印刷と印刷プレビューのサポートとして、ドキュメント/ビューアーキテクチャに基づいています。

すべての MFC アプリケーションには、少なくとも2つのオブジェクト (から派生したアプリケーションオブジェクト [`CWinApp`](reference/cwinapp-class.md) と、から派生した主なウィンドウオブジェクト) があり [`CWnd`](reference/cwnd-class.md) ます。 (ほとんどの場合、メインウィンドウは、、 [`CFrameWnd`](reference/cframewnd-class.md) [`CMDIFrameWnd`](reference/cmdiframewnd-class.md) またはから派生しますが、 [`CDialog`](reference/cdialog-class.md) これらはすべてから派生 `CWnd` します)。

ドキュメント/ビューアーキテクチャを使用するアプリケーションには、追加のオブジェクトが含まれています。 主要なオブジェクトは次のとおりです。

- [`CWinApp`](reference/cwinapp-class.md)前に説明したように、クラスから派生したアプリケーションオブジェクト。
- クラスから派生した1つ以上のドキュメントクラスオブジェクト [`CDocument`](reference/cdocument-class.md) 。 ドキュメントクラスオブジェクトは、ビューで操作されるデータの内部表現を担います。 データファイルに関連付けられている可能性があります。
- クラスから派生した1つ以上のビューオブジェクト [`CView`](reference/cview-class.md) 。 各ビューは、ドキュメントにアタッチされ、フレームウィンドウに関連付けられているウィンドウです。 ビューは、ドキュメントクラスオブジェクトに含まれるデータを表示および操作します。

ドキュメント/ビューアプリケーションには、フレームウィンドウ (から派生 [`CFrameWnd`](reference/cframewnd-class.md) ) とドキュメントテンプレート (から派生) も含まれて [`CDocTemplate`](reference/cdoctemplate-class.md) います。

## <a name="see-also"></a>関連項目

[クラスの概要](class-library-overview.md)