---
title: 'ActiveX コントロール コンテナー : コントロール プロパティの表示と変更'
ms.date: 11/04/2016
helpviewer_keywords:
- properties [MFC], viewing and modifying
- ActiveX control containers [MFC], viewing and modifying properties
- resource editors, viewing and modifying ActiveX controls
- ActiveX controls [MFC], properties
- controls [MFC], properties
ms.assetid: 14ce5152-742b-4e0d-a9ab-c7b456e32918
ms.openlocfilehash: abddda015a80b21d941409044524e2f526b26f08
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454942"
---
# <a name="activex-control-containers-viewing-and-modifying-control-properties"></a>ActiveX コントロール コンテナー : コントロール プロパティの表示と変更

プロジェクトに ActiveX コントロールを挿入するときは、表示したり、ActiveX コントロールでサポートされるプロパティを変更すると便利です。 この記事では、これを行う Visual C リソース エディターを使用する方法について説明します。

ActiveX コントロール コンテナー アプリケーションでは、埋め込まれたコントロールを使用する場合は、表示し、リソース エディターで、コントロールのプロパティを変更します。 デザイン時にプロパティ値を設定するのにリソース エディターを使用することもできます。 リソース エディターは、プロジェクトのリソース ファイルで、これらの値を自動的に保存されます。 コントロールの任意のインスタンスはこれらの値に初期化され、そのプロパティになります。

この手順をプロジェクトにコントロールを挿入することを前提としています。 詳しくは、次を参照してください。 [ActiveX コントロール コンテナー: コントロール コンテナー アプリケーションへのコントロールを挿入する](../mfc/inserting-a-control-into-a-control-container-application.md)します。

コントロールのプロパティを表示するのには、最初の手順では、プロジェクトのダイアログ テンプレートに、コントロールのインスタンスを追加します。

### <a name="to-view-the-properties-of-a-control"></a>コントロールのプロパティを表示するには

1. リソース ビューで、開く、**ダイアログ**フォルダー。

1. [メイン] ダイアログ ボックスのテンプレートを開きます。

1. ActiveX コントロールを使用して、挿入、 **ActiveX コントロールの挿入** ダイアログ ボックス。 詳細については、次を参照してください。[表示およびダイアログ ボックスに ActiveX コントロールを追加](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md)します。

1. ダイアログ ボックスでは、ActiveX コントロールを選択します。

1. [プロパティ] ウィンドウからをクリックして、**プロパティ**ボタンをクリックします。

使用して、**プロパティ** ダイアログ ボックスを変更してすぐに新しいプロパティをテストします。

## <a name="see-also"></a>関連項目

[ActiveX コントロール コンテナー](../mfc/activex-control-containers.md)

