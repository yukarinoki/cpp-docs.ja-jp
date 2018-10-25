---
title: レコード ビュー (MFC データ アクセス) の使用 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views, customizing default code
ms.assetid: 91f2828f-0666-4273-ae28-e4703fd98521
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3af338f4c88b2fa7268387ef0701f52a813b0d49
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50056200"
---
# <a name="using-a-record-view--mfc-data-access"></a>レコード ビューの使用法 (MFC データ アクセス)

このトピックでは、ウィザードで生成したレコード ビュー用の既定のコードをカスタマイズする一般的な方法について説明します。 によるレコードの選択を制限したい、通常、[フィルター](../data/odbc/recordset-filtering-records-odbc.md)または[パラメーター](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)、おそらく[並べ替え](../data/odbc/recordset-sorting-records-odbc.md)レコードは、SQL ステートメントをカスタマイズします。

使用して`CRecordView`と同じです[CFormView](../mfc/reference/cformview-class.md)します。 基本的には、レコード ビューを使用して、1 つのレコードセットのレコードを表示し、場合によっては更新します。 さらに、同様で説明したように他のレコード セットを使用したい場合があります[レコード ビュー: セカンド レコード セットからリスト ボックス](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)します。

## <a name="see-also"></a>関連項目

[レコード ビュー (MFC データ アクセス)](../data/record-views-mfc-data-access.md)<br/>
[ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)