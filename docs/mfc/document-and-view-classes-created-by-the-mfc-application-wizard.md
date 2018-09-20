---
title: 文書化し、MFC アプリケーション ウィザードで作成されるクラスの表示 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- document classes [MFC]
- document classes [MFC], created by application wizards
- application wizards [MFC], document/view classes created
- view classes [MFC], created by application wizards
ms.assetid: 70c34a60-2701-4981-acea-c08a5787d8e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb1a1fc6c35bfb9589e827d798cb112640fa9b2f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417619"
---
# <a name="document-and-view-classes-created-by-the-mfc-application-wizard"></a>MFC のアプリケーション ウィザードで作成されるドキュメント クラスとビュー クラス

MFC アプリケーション ウィザードできますスタートが切れますので、プログラム開発のスケルトンのドキュメントとビュー クラスを作成しています。 できます[コマンドとメッセージをこれらのクラスにマップ](../mfc/reference/mapping-messages-to-functions.md)Visual C ソース コード エディターを使用して、そのメンバー関数を記述するとします。

クラスから派生した MFC アプリケーション ウィザードによって作成されたドキュメント クラスは[CDocument](../mfc/reference/cdocument-class.md)します。 ビュー クラスから派生[CView](../mfc/reference/cview-class.md)します。 アプリケーション ウィザード ダイアログ ボックスに指定した名前のアプリケーション ウィザードにはこれらのクラスをこれらを含むファイルがプロジェクト名に基づきます。 アプリケーション ウィザードでは、既定の名前を変更するのに [クラスの生成] ページを使用できます。

一部のアプリケーションには、1 つ以上のドキュメント クラス、ビュー クラス、またはフレーム ウィンドウ クラスを必要があります。 詳細については、次を参照してください。[複数のドキュメント タイプ、ビュー、およびフレーム Windows](../mfc/multiple-document-types-views-and-frame-windows.md)します。

## <a name="see-also"></a>関連項目

[ドキュメント/ビュー アーキテクチャ](../mfc/document-view-architecture.md)

