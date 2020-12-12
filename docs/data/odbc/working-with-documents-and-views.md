---
description: '詳細情報: ドキュメントとビューの操作'
title: ドキュメントとビューの使用
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], documents
- MFC [C++], views
- views [C++], MFC
- documents [C++], MFC
ms.assetid: 349b142d-1c5a-4b99-9de4-241e41d3d2f1
ms.openlocfilehash: 5e2842e9edd3dca566fa030579fae6cd743e3802
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319184"
---
# <a name="working-with-documents-and-views"></a>ドキュメントとビューの使用

Microsoft Foundation Classes (MFC) ライブラリは、その機能の多くについて、ドキュメント/ビューアーキテクチャに依存しています。 通常、ドキュメントはデータを格納し、ビューはフレームウィンドウのクライアント領域内に表示し、データとのユーザー操作を管理します。 ビューは、ドキュメントと通信してデータを取得および更新します。 データベースクラスは、フレームワークと共に使用することも、使用することもできません。

フレームワークでデータベースクラスを使用する方法の詳細については、「 [MFC: ドキュメントおよびビューでのデータベースクラスの使用](../../data/mfc-using-database-classes-with-documents-and-views.md)」を参照してください。

既定では、MFC アプリケーションウィザードでは、データベースをサポートしていないスケルトンアプリケーションが作成されます。 ただし、最小データベースサポートまたは完全なフォームベースのサポートを含めるためのオプションを選択できます。 アプリケーションウィザードのオプションの詳細については、「 [[データベースサポート] (MFC アプリケーションウィザード](../../mfc/reference/database-support-mfc-application-wizard.md))」を参照してください。

また、完全なドキュメント/ビューアーキテクチャを使用せずにデータベースクラスを使用することもできます。 詳細については、「 [MFC: ドキュメントとビューを使用しないデータベースクラスの使用](../../data/mfc-using-database-classes-without-documents-and-views.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ODBC と MFC](../../data/odbc/odbc-and-mfc.md)
