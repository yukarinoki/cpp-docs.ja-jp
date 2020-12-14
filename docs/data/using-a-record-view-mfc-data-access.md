---
description: 詳細については、「レコードビューの使用 (MFC データアクセス)」を参照してください。
title: レコード ビューの使用法 (MFC データ アクセス)
ms.date: 11/04/2016
helpviewer_keywords:
- record views, customizing default code
ms.assetid: 91f2828f-0666-4273-ae28-e4703fd98521
ms.openlocfilehash: f79e5df4c967b89b02245fb03a3e4e269894b835
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239663"
---
# <a name="using-a-record-view--mfc-data-access"></a>レコード ビューの使用法 (MFC データ アクセス)

このトピックでは、ウィザードで生成したレコード ビュー用の既定のコードをカスタマイズする一般的な方法について説明します。 通常は、 [フィルター](../data/odbc/recordset-filtering-records-odbc.md) または [パラメーター](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)を使用してレコードの選択を制限します。たとえば、レコードを [並べ替える](../data/odbc/recordset-sorting-records-odbc.md) には、SQL ステートメントをカスタマイズします。

の使用方法 `CRecordView` は、 [CFormView](../mfc/reference/cformview-class.md)を使用する場合とほぼ同じです。 基本的には、レコード ビューを使用して、1 つのレコードセットのレコードを表示し、場合によっては更新します。 それ以外の場合は、「 [レコードビュー: 2 番目のレコードセットからリストボックスに入力](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)する」で説明されているように、他のレコードセットを使用することもできます。

## <a name="see-also"></a>関連項目

[レコードビュー (MFC データアクセス)](../data/record-views-mfc-data-access.md)<br/>
[ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)
