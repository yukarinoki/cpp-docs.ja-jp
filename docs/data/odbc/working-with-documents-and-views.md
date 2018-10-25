---
title: ドキュメントとビューの操作 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], documents
- MFC [C++], views
- views [C++], MFC
- documents [C++], MFC
ms.assetid: 349b142d-1c5a-4b99-9de4-241e41d3d2f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c3879c6a29f95cc908d12c0b899214b521f46686
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50060444"
---
# <a name="working-with-documents-and-views"></a>ドキュメントとビューの使用

Microsoft Foundation Classes (MFC) ライブラリは、その機能の多くのドキュメント/ビュー アーキテクチャに依存します。 通常、ドキュメントは、データを格納し、ビュー フレーム ウィンドウのクライアント領域内に表示して、データとユーザーの対話を管理します。 ビューは、ドキュメントを取得し、データの更新と通信します。 フレームワークなしでも、データベース クラスを使用することができます。

データベース クラスをフレームワークに使用する方法の詳細については、次を参照してください。 [MFC: ドキュメントとビューを用いたデータベース クラス](../../data/mfc-using-database-classes-with-documents-and-views.md)します。

既定では、MFC アプリケーション ウィザードは、データベースはサポートされていない、スケルトン アプリケーションを作成します。 ただし、最小限のデータベースのサポートまたはフォーム ベースのより完全なサポートを追加するオプションを選択できます。 アプリケーション ウィザードのオプションの詳細については、次を参照してください。[データベースのサポート、MFC アプリケーション ウィザード](../../mfc/reference/database-support-mfc-application-wizard.md)します。

完全なドキュメント/ビュー アーキテクチャを使用せず、データベース クラスを使用することもできます。 詳細については、次を参照してください。 [MFC: 用いないデータベース クラスとビュー](../../data/mfc-using-database-classes-without-documents-and-views.md)します。

## <a name="see-also"></a>関連項目

[ODBC と MFC](../../data/odbc/odbc-and-mfc.md)