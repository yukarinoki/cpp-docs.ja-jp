---
description: 詳細については、「MFC アプリケーションウィザードで作成されるドキュメントクラスとビュークラス」を参照してください。
title: MFC のアプリケーション ウィザードで作成されるドキュメント クラスとビュー クラス
ms.date: 11/04/2016
helpviewer_keywords:
- document classes [MFC]
- document classes [MFC], created by application wizards
- application wizards [MFC], document/view classes created
- view classes [MFC], created by application wizards
ms.assetid: 70c34a60-2701-4981-acea-c08a5787d8e6
ms.openlocfilehash: f182278ebdd971364e3e35e15e51b6ea5e7aaf68
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330313"
---
# <a name="document-and-view-classes-created-by-the-mfc-application-wizard"></a>MFC のアプリケーション ウィザードで作成されるドキュメント クラスとビュー クラス

MFC アプリケーションウィザードでは、スケルトンドキュメントとビュークラスを作成することにより、プログラムの開発を開始できます。 その後、 [コマンドとメッセージをこれらのクラスにマップ](reference/mapping-messages-to-functions.md) し、Visual C++ ソースコードエディターを使用してそのメンバー関数を記述できます。

MFC アプリケーションウィザードによって作成されるドキュメントクラスは、 [CDocument](reference/cdocument-class.md)クラスから派生します。 ビュークラスは、 [CView](reference/cview-class.md)から派生します。 アプリケーションウィザードによってこれらのクラスが提供される名前と、これらのクラスを含むファイルは、[アプリケーションウィザード] ダイアログボックスで指定したプロジェクト名に基づいています。 アプリケーションウィザードでは、[生成されたクラス] ページを使用して、既定の名前を変更できます。

アプリケーションによっては、複数のドキュメントクラス、ビュークラス、またはフレームウィンドウクラスが必要になる場合があります。 詳細については、「 [複数のドキュメントの種類、ビュー、フレームウィンドウ](multiple-document-types-views-and-frame-windows.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ドキュメント/ビューアーキテクチャ](document-view-architecture.md)
