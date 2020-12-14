---
description: '詳細については、「ActiveX コントロールコンテナー: コントロールのプロパティの表示と変更」を参照してください。'
title: 'ActiveX コントロール コンテナー : コントロール プロパティの表示と変更'
ms.date: 11/04/2016
helpviewer_keywords:
- properties [MFC], viewing and modifying
- ActiveX control containers [MFC], viewing and modifying properties
- resource editors, viewing and modifying ActiveX controls
- ActiveX controls [MFC], properties
- controls [MFC], properties
ms.assetid: 14ce5152-742b-4e0d-a9ab-c7b456e32918
ms.openlocfilehash: 27de4773bfb42b7caf759a64bbbfc0c6b81bcdba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197661"
---
# <a name="activex-control-containers-viewing-and-modifying-control-properties"></a>ActiveX コントロール コンテナー : コントロール プロパティの表示と変更

ActiveX コントロールをプロジェクトに挿入する場合は、ActiveX コントロールでサポートされているプロパティを表示および変更すると便利です。 この記事では、Visual C++ リソースエディターを使用してこれを行う方法について説明します。

ActiveX コントロールコンテナーアプリケーションで埋め込みコントロールを使用している場合は、リソースエディターでコントロールのプロパティを表示および変更できます。 また、リソースエディターを使用して、デザイン時にプロパティ値を設定することもできます。 リソースエディターは、これらの値をプロジェクトのリソースファイルに自動的に保存します。 その後、コントロールのすべてのインスタンスのプロパティが、これらの値に初期化されます。

この手順では、プロジェクトにコントロールが挿入されていることを前提としています。 詳細については、「 [ActiveX コントロールコンテナー: コントロールコンテナーアプリケーションへのコントロールの挿入](inserting-a-control-into-a-control-container-application.md)」を参照してください。

コントロールのプロパティを表示するための最初の手順は、コントロールのインスタンスをプロジェクトのダイアログテンプレートに追加することです。

### <a name="to-view-the-properties-of-a-control"></a>コントロールのプロパティを表示するには

1. リソースビューで、 **ダイアログ** フォルダーを開きます。

1. メインダイアログボックステンプレートを開きます。

1. [ **Activex コントロールの挿入** ] ダイアログボックスを使用して activex コントロールを挿入します。 詳細については、「 [ダイアログボックスへの ActiveX コントロールの表示と追加](../windows/adding-editing-or-deleting-controls.md)」を参照してください。

1. ダイアログボックスで ActiveX コントロールを選択します。

1. [ **プロパティ** ] ウィンドウで、[ **プロパティ** ] ボタンをクリックします。

[ **プロパティ** ] ダイアログボックスを使用すると、新しいプロパティをすぐに変更およびテストできます。

## <a name="see-also"></a>関連項目

[ActiveX コントロールコンテナー](activex-control-containers.md)
