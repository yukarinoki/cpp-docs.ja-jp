---
title: 設計と、レコード ビュー (MFC データ アクセス) を作成する |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- designing forms
- record views, creating
- forms [C++], designing
- record views, designing
- application wizards [C++], creating record view classes
- designing record views
ms.assetid: 1d6f5439-754f-4b8b-a19d-841a4657827b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c03b85538a795142f5085c93df3a60f4c60481ab
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50065851"
---
# <a name="designing-and-creating-a-record-view--mfc-data-access"></a>レコード ビューのデザインと作成 (MFC データ アクセス)

使用してレコード ビュー クラスを作成することができます、 [MFC アプリケーション ウィザード](../mfc/reference/database-support-mfc-application-wizard.md)します。 アプリケーション ウィザードを使用すると、レコード ビュー クラスと、それに対応するダイアログ テンプレート リソース (コントロールは含まれません) が作成されます。 ダイアログ テンプレート リソースにコントロールを追加するには、Visual C++ ダイアログ エディターを使用する必要があります。 その一方で使用する場合に**クラスの追加**、最初にダイアログ テンプレート リソースを作成 ダイアログ ボックス エディターし、レコード ビュー クラスを作成する必要があります。

#### <a name="to-create-your-record-view-with-the-mfc-application-wizard"></a>MFC アプリケーション ウィザードを使用してレコード ビューを作成するには

1. 参照してください[データベース サポート、MFC アプリケーション ウィザード](../mfc/reference/database-support-mfc-application-wizard.md)します。

#### <a name="to-design-your-form"></a>フォームをデザインするには

1. 参照してください[ダイアログ エディター](../windows/dialog-editor.md)します。

#### <a name="to-create-your-record-view-class"></a>レコード ビュー クラスを作成するには

1. 参照してください[MFC ODBC コンシューマーの追加](../mfc/reference/adding-an-mfc-odbc-consumer.md)します。

次のトピックでは、レコード ビューの使用に関するいくつかの事項について詳しく説明しています。

- [レコード ビュー: レコード ビュー内のナビゲーションのサポート](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)

- [レコード ビュー: レコード ビューの使用](../data/using-a-record-view-mfc-data-access.md)

- [レコード ビュー: セカンド レコード セットからリスト ボックスの入力](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)

## <a name="see-also"></a>関連項目

[レコード ビュー (MFC データ アクセス)](../data/record-views-mfc-data-access.md)<br/>
[レコードセット (ODBC)](../data/odbc/recordset-odbc.md)<br/>
[ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)