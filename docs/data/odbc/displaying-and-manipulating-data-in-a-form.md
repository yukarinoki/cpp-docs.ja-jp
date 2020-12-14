---
description: '詳細情報: フォームでのデータの表示と操作'
title: フォームでのデータの表示と操作
ms.date: 11/04/2016
helpviewer_keywords:
- forms [C++], displaying data
- displaying data [C++], forms
- ODBC [C++], forms
- record views [C++], displaying data
- data [MFC]
- data [MFC], displaying in a form
ms.assetid: c56185c4-12cb-40b1-b499-02b29ea83e3a
ms.openlocfilehash: 151e4036830f4923fbed2e609535edf3beacee5f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97252325"
---
# <a name="displaying-and-manipulating-data-in-a-form"></a>フォームでのデータの表示と操作

多くのデータアクセスアプリケーションでは、データが選択され、フォームのフィールドに表示されます。 データベースクラス [CRecordView](../../mfc/reference/crecordview-class.md) は、レコードセットオブジェクトに直接接続された [CFormView](../../mfc/reference/cformview-class.md) オブジェクトを提供します。 レコードビューは、 [ダイアログデータエクスチェンジ (DDX)](../../mfc/dialog-data-exchange-and-validation.md) を使用して、現在のレコードのフィールドの値をレコードセットからフォーム上のコントロールに移動し、更新された情報をレコードセットに戻します。 レコードセットは、レコードフィールドエクスチェンジ (RFX) を使用して、フィールドデータメンバーと、データソース上のテーブル内の対応する列との間でデータを移動します。

MFC アプリケーションウィザードを使用するか、「 [MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)」で説明されているように **クラスを追加** すると、ビュークラスとそれに関連するレコードセットクラスを組み合わせて作成できます。

レコードビューとそのレコードセットは、ドキュメントを閉じると破棄されます。 レコードビューの詳細については、「 [レコードビュー](../../data/record-views-mfc-data-access.md)」を参照してください。 RFX の詳細については、「 [レコードフィールドエクスチェンジ (rfx)](../../data/odbc/record-field-exchange-rfx.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ODBC と MFC](../../data/odbc/odbc-and-mfc.md)
