---
description: '詳細情報: OLE アプリケーションを作成するための一連の操作'
title: OLE アプリケーションの作成手順
ms.date: 11/04/2016
helpviewer_keywords:
- OLE applications [MFC], creating
- OLE applications [MFC]
- applications [OLE], creating
- applications [OLE]
ms.assetid: 84b0f606-36c1-4253-9cea-44427f0074b9
ms.openlocfilehash: 2bce49d569c6d3def536cbe9386cafbe08ccdbfb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217563"
---
# <a name="sequence-of-operations-for-creating-ole-applications"></a>OLE アプリケーションの作成手順

次の表は、OLE リンクと埋め込みアプリケーションの作成におけるロールとフレームワークの役割を示しています。 これらは、実行する一連の手順ではなく、使用可能なオプションを表します。

### <a name="creating-ole-applications"></a>OLE アプリケーションの作成

|タスク|そうですよね|フレームワークは|
|----------|------------|------------------------|
|COM コンポーネントを作成します。|MFC アプリケーションウィザードを実行します。 [**複合ドキュメントのサポート**] タブで、[**フルサーバー** ] または [**ミニサーバー** ] を選択します。|フレームワークによって、COM コンポーネント機能が有効になっているスケルトンアプリケーションが生成されます。 すべての COM 機能は、わずかな変更だけで既存のアプリケーションに転送できます。|
|コンテナーアプリケーションを最初から作成します。|MFC アプリケーションウィザードを実行します。 [**複合ドキュメントサポート**] タブで [**コンテナー** ] を選択します。クラスビューを使用して、ソースコードエディターにアクセスします。 COM ハンドラー関数のコードを入力します。|フレームワークは、COM コンポーネント (サーバー) アプリケーションによって作成された COM オブジェクトを挿入できるスケルトンアプリケーションを生成します。|
|最初からオートメーションをサポートするアプリケーションを作成します。|MFC アプリケーションウィザードを実行します。 **[高度な機能**] タブで [**オートメーション**] を選択します。アプリケーションのメソッドとプロパティをオートメーション用に公開するには、クラスビューを使用します。|フレームワークは、他のアプリケーションによってアクティブ化および自動化できるスケルトンアプリケーションを生成します。|

## <a name="see-also"></a>関連項目

[フレームワークでのビルド](../mfc/building-on-the-framework.md)<br/>
[MFC アプリケーションをビルドするための一連の操作](../mfc/sequence-of-operations-for-building-mfc-applications.md)<br/>
[ActiveX コントロールを作成するための一連の操作](../mfc/sequence-of-operations-for-creating-activex-controls.md)<br/>
[データベースアプリケーションを作成するための一連の操作](../mfc/sequence-of-operations-for-creating-database-applications.md)
