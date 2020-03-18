---
title: MFC アプリケーション アーキテクチャ クラス
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, classes
- MFC, application development
- classes [MFC], MFC
- application architecture classes [MFC]
ms.assetid: 71b2de54-b44d-407e-9c71-9baf954e18d9
ms.openlocfilehash: 1e09447623b32e9b10063af5bc91ac9589f45e44
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447725"
---
# <a name="mfc-application-architecture-classes"></a>MFC アプリケーション アーキテクチャ クラス

このカテゴリのクラスは、フレームワークアプリケーションのアーキテクチャに寄与します。 ほとんどのアプリケーションに共通の機能を提供します。 アプリケーション固有の機能を追加するには、フレームワークに入力します。 通常は、アーキテクチャクラスから新しいクラスを派生させ、新しいメンバーを追加するか、既存のメンバー関数をオーバーライドします。

[アプリケーションウィザード](../mfc/reference/mfc-application-wizard.md)では、アプリケーションフレームワークをさまざまな方法で使用する、複数の種類のアプリケーションが生成されます。 SDI (シングルドキュメントインターフェイス) と MDI (マルチドキュメントインターフェイス) アプリケーションでは、ドキュメント/ビューアーキテクチャと呼ばれるフレームワークの一部が完全に使用されます。 ダイアログベースのアプリケーション、フォームベースのアプリケーション、Dll など、他の種類のアプリケーションでは、ドキュメント/ビューアーキテクチャの機能の一部のみを使用します。

ドキュメント/ビューアプリケーションには、ドキュメント、ビュー、およびフレームウィンドウの1つ以上のセットが含まれています。 ドキュメントテンプレートオブジェクトは、各ドキュメント/ビュー/フレームセットのクラスを関連付けます。

MFC アプリケーションでドキュメント/ビューアーキテクチャを使用する必要はありませんが、そのためにはさまざまな利点があります。 MFC OLE コンテナーとサーバーのサポートは、印刷と印刷プレビューのサポートとして、ドキュメント/ビューアーキテクチャに基づいています。

すべての MFC アプリケーションには、少なくとも2つのオブジェクトがあります。 [CWinApp](../mfc/reference/cwinapp-class.md)から派生したアプリケーションオブジェクトと、 [CWnd](../mfc/reference/cwnd-class.md)から派生した (多くの場合は間接的に) メインウィンドウオブジェクトです。 (ほとんどの場合、メインウィンドウは、`CWnd`から派生した[CFrameWnd](../mfc/reference/cframewnd-class.md)、 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)、または[CDialog](../mfc/reference/cdialog-class.md)から派生します)。

ドキュメント/ビューアーキテクチャを使用するアプリケーションには、追加のオブジェクトが含まれています。 プリンシパルオブジェクトは次のとおりです。

- 前に説明したように、クラス[CWinApp](../mfc/reference/cwinapp-class.md)から派生したアプリケーションオブジェクト。

- [CDocument](../mfc/reference/cdocument-class.md)クラスから派生した1つ以上のドキュメントクラスオブジェクト。 ドキュメントクラスオブジェクトは、ビューで操作されるデータの内部表現を担います。 データファイルに関連付けられている可能性があります。

- クラス[CView](../mfc/reference/cview-class.md)から派生した1つ以上のビューオブジェクト。 各ビューは、ドキュメントにアタッチされ、フレームウィンドウに関連付けられているウィンドウです。 ビューは、ドキュメントクラスオブジェクトに含まれるデータを表示および操作します。

ドキュメント/ビューアプリケーションには、( [CFrameWnd](../mfc/reference/cframewnd-class.md)から派生した) フレームウィンドウとドキュメントテンプレート ( [CDocTemplate](../mfc/reference/cdoctemplate-class.md)から派生) も含まれています。

## <a name="see-also"></a>参照

[クラスの概要](../mfc/class-library-overview.md)
