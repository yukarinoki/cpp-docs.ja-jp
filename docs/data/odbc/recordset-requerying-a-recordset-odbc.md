---
title: 'レコードセット: クエリの再実行 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets, requerying
- requerying recordsets
- Requery method
- ODBC recordsets, requerying
- refreshing recordsets
ms.assetid: 4ebc3b5b-5b91-4f51-a967-245223c6b8e1
ms.openlocfilehash: b7cf40ca3b0c8e415368772063aee61008a52764
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212785"
---
# <a name="recordset-requerying-a-recordset-odbc"></a>レコードセット: クエリの再実行 (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

このトピックでは、レコードセットオブジェクトを使用して、データベースからのクエリを再実行する (つまり更新する) 方法と、 [requery](../../mfc/reference/crecordset-class.md#requery)メンバー関数を使用して実行する方法について説明します。

レコードセットを再クエリする主な理由は次のとおりです。

- 自分が追加したレコード、他のユーザーが削除したレコード、他のユーザーによって削除されたレコードに対して、レコードセットを最新の状態にします (削除したレコードは既にレコードセットに反映されています)。

- パラメーター値の変更に基づいてレコードセットを更新します。

##  <a name="bringing-the-recordset-up-to-date"></a><a name="_core_bringing_the_recordset_up_to_date"></a>レコードセットを最新の状態にする

多くの場合、レコードセットオブジェクトを再クエリして最新の状態にする必要があります。 マルチユーザーデータベース環境では、レコードセットの有効期間中に他のユーザーがデータに変更を加えることができます。 他のユーザーによって加えられた変更をレコードセットに反映する場合と、他のユーザーのレコードセットが変更を反映する場合の詳細については、「[レコードセット: レコード更新のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)と[ダイナセット](../../data/odbc/dynaset.md)」を参照してください。

##  <a name="requerying-based-on-new-parameters"></a><a name="_core_requerying_based_on_new_parameters"></a>新しいパラメーターに基づいた再クエリ

もう1つのよくあることと同様に、 [Requery](../../mfc/reference/crecordset-class.md#requery)の使用は、パラメーター値の変更に基づいて新しいレコードセットを選択することです。

> [!TIP]
>  `Open` を再度呼び出す場合よりもパラメーター値を変更して `Requery` を呼び出すと、クエリ速度が大幅に速くなることがあります。

##  <a name="requerying-dynasets-vs-snapshots"></a><a name="_core_requerying_dynasets_vs.._snapshots"></a>ダイナセットとスナップショットの再クエリ

ダイナセットは動的な最新データを含む一連のレコードを提示することを目的としているため、他のユーザーの追加を反映する場合は、多くの場合、ダイナセットを再クエリする必要があります。 一方、スナップショットは、レポートの準備、合計の計算などを行うときに静的コンテンツに安全に依存できるので便利です。 ただし、場合によっては、スナップショットの再クエリも必要になることがあります。 マルチユーザー環境では、他のユーザーがデータベースを変更したときに、スナップショットデータとデータソースとの同期が失われることがあります。

#### <a name="to-requery-a-recordset-object"></a>レコードセットオブジェクトを再クエリするには

1. オブジェクトの[Requery](../../mfc/reference/crecordset-class.md#requery)メンバー関数を呼び出します。

または、元のレコードセットを閉じて再度開くこともできます。 どちらの場合も、新しいレコードセットはデータソースの現在の状態を表します。

例については、「[レコードビュー: 2 番目のレコードセットからリストボックスに入力](../../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)する」を参照してください。

> [!TIP]
>  `Requery` のパフォーマンスを最適化するには、レコードセットの[フィルター](../../data/odbc/recordset-filtering-records-odbc.md)または[並べ替え](../../data/odbc/recordset-sorting-records-odbc.md)を変更しないようにします。 `Requery`を呼び出す前に、パラメーター値のみを変更してください。

`Requery` の呼び出しが失敗した場合は、呼び出しを再試行できます。それ以外の場合は、アプリケーションを正常に終了する必要があります。 `Requery` または `Open` の呼び出しは、さまざまな理由で失敗する可能性があります。 ネットワークエラーが発生した可能性があります。または、の呼び出し中に、既存のデータがリリースされた後、新しいデータが取得される前に、別のユーザーが排他アクセスを取得する可能性があります。または、レコードセットが依存しているテーブルを削除することもできます。

## <a name="see-also"></a>参照

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: データ列を動的に結びつける方法 (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)<br/>
[レコードセット: レコードセットの生成と破棄 (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)
