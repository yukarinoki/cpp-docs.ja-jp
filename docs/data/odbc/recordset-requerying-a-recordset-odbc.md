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
ms.openlocfilehash: cdae28f81eebe8427bc829072e0d9a83c6ec1722
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366944"
---
# <a name="recordset-requerying-a-recordset-odbc"></a>レコードセット: クエリの再実行 (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

このトピックでは、レコードセット オブジェクトを使用してデータベースから自身を再クエリ (更新) する方法と[、Requery](../../mfc/reference/crecordset-class.md#requery)メンバー関数でクエリを実行するタイミングについて説明します。

レコードセットを再クエリする主な理由は、次のとおりです。

- 自分や他のユーザーが追加したレコード、および他のユーザーによって削除されたレコードに関して、レコードセットを最新の状態にします (削除したレコードは既にレコードセットに反映されます)。

- 変更されたパラメータ値に基づいてレコードセットを更新します。

## <a name="bringing-the-recordset-up-to-date"></a><a name="_core_bringing_the_recordset_up_to_date"></a>レコードセットを最新の状態にする

多くの場合、レコードセット オブジェクトを再クエリして最新の状態にします。 マルチユーザー データベース環境では、他のユーザーがレコードセットの存続期間中にデータを変更できます。 レコードセットが他のユーザーによる変更を反映するタイミングと、他のユーザーのレコードセットに変更が反映されるタイミングの詳細については、「[レコードセット: レコードセットがレコードを更新する方法 (ODBC)」](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)および「[ダイナセット](../../data/odbc/dynaset.md)」を参照してください。

## <a name="requerying-based-on-new-parameters"></a><a name="_core_requerying_based_on_new_parameters"></a>新しいパラメータに基づく再クエリ

もう 1 つの頻繁な (同様に重要) [Requery](../../mfc/reference/crecordset-class.md#requery)の使用は、パラメータ値の変更に基づいて新しいレコードセットを選択することです。

> [!TIP]
> パラメータ値を変更して呼び出`Requery`す場合、クエリ速度は、再度呼`Open`び出す場合よりも大幅に高速です。

## <a name="requerying-dynasets-vs-snapshots"></a><a name="_core_requerying_dynasets_vs.._snapshots"></a>ダイナセットとスナップショットの再クエリ

ダイナセットは動的な最新データを持つレコードのセットを提示することを意図しているので、他のユーザーの追加を反映したい場合は、ダイナセットを頻繁に再クエリする必要があります。 一方、スナップショットは、レポートの準備や合計の計算などを行う際に、静的な内容に安全に依存できるため便利です。 それでも、スナップショットを再クエリする場合もあります。 マルチユーザー環境では、他のユーザーがデータベースを変更すると、スナップショット データがデータ ソースと同期できなくなる場合があります。

#### <a name="to-requery-a-recordset-object"></a>レコードセット オブジェクトを再クエリするには

1. オブジェクトの[Requery](../../mfc/reference/crecordset-class.md#requery)メンバー関数を呼び出します。

または、元のレコードセットを閉じて再度開くことができます。 いずれの場合も、新しいレコードセットはデータ ソースの現在の状態を表します。

例については、「[レコード ビュー : 2 番目のレコードセットからリスト ボックスを塗りつぶす](../../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)」を参照してください。

> [!TIP]
> パフォーマンスを`Requery`最適化するには、レコードセットの[フィルタ](../../data/odbc/recordset-filtering-records-odbc.md)または[並べ替えを](../../data/odbc/recordset-sorting-records-odbc.md)変更しないでください。 を呼び出す`Requery`前にパラメータ値のみを変更します。

呼び`Requery`出しが失敗した場合は、呼び出しを再試行できます。それ以外の場合、アプリケーションは正常に終了する必要があります。 呼び出`Requery`し`Open`が失敗する場合、またはいくつかの理由で失敗する可能性があります。 ネットワーク エラーが発生した可能性があります。また、呼び出し中に既存のデータが解放された後、新しいデータが取得される前に、別のユーザーが排他的アクセスを取得する可能性があります。または、レコードセットが依存しているテーブルを削除できます。

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: データ列を動的に結びつける方法 (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)<br/>
[レコードセット: レコードセットの生成と破棄 (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)
