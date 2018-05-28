---
title: 'レコード セット: クエリの再実行 (ODBC) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- recordsets, requerying
- requerying recordsets
- Requery method
- ODBC recordsets, requerying
- refreshing recordsets
ms.assetid: 4ebc3b5b-5b91-4f51-a967-245223c6b8e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a3157f416cf6fb7e0fd3b5ad4797b83de218c9ef
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="recordset-requerying-a-recordset-odbc"></a>レコードセット: クエリの再実行 (ODBC)
このトピックの内容は、MFC ODBC クラスに該当します。  
  
 このトピックでは、クエリを再実行をレコード セット オブジェクトを使用する方法について説明します (つまりの更新) 自体をデータベースから、/で実現することができます、 [Requery](../../mfc/reference/crecordset-class.md#requery)メンバー関数。  
  
 クエリの再実行するプリンシパルの理由は次のとおりです。  
  
-   ユーザーまたは他のユーザーによって追加されたレコードとその他のユーザー (を削除するものは既に、レコード セット内で反映されます) によって削除されたレコードに関する最新のレコード セットを表示します。  
  
-   パラメーター値の変更に基づいて、レコード セットを更新します。  
  
##  <a name="_core_bringing_the_recordset_up_to_date"></a> 日付のレコード セットを取り込む  
 多くの場合、するために、レコード セット オブジェクトを再実行最新の状態。 環境では、マルチ ユーザー データベース、他のユーザーを変更できるデータ、レコード セットの有効期間にします。 詳細については、レコード セットが他のユーザーによって行われた変更を反映するときと、その他のユーザーのレコード セットが、変更を反映するときに、次を参照してください[レコード セット: レコード更新のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)と[ダイナセット](../../data/odbc/dynaset.md)。  
  
##  <a name="_core_requerying_based_on_new_parameters"></a> 新しいパラメーターに基づくクエリを再実行  
 他の頻繁な — と同様に重要な — の使用[Requery](../../mfc/reference/crecordset-class.md#requery)パラメーター値を変更に基づくレコードの新しいセットを選択することです。  
  
> [!TIP]
>  クエリの速度が速く処理を呼び出す場合**Requery**を呼び出した場合よりもパラメーター値を変更して**開く**もう一度です。  
  
##  <a name="_core_requerying_dynasets_vs.._snapshots"></a> ダイナセットを使う場合とクエリを再実行します。スナップショット  
 ダイナセットを使う場合は、動的な最新の状態データのレコードのセットが表示になっているために、クエリを他のユーザーの追加機能を反映する場合に多くの場合は、ダイナセットを再実行する必要があります。 その一方で、レポートの準備や集計計算などを実行するときに安全にその静的なコンテンツに依存することができますので、スナップショットに役立ちます。 それでももスナップショットを再実行することがもできます。 マルチ ユーザー環境の場合は、スナップショット データを他のユーザー データベースの変更がデータ ソースとの同期を失う可能性があります。  
  
#### <a name="to-requery-a-recordset-object"></a>レコード セット オブジェクトを再実行するには  
  
1.  呼び出す、 [Requery](../../mfc/reference/crecordset-class.md#requery)オブジェクトのメンバー関数。  
  
 または、することが閉じてから、元のレコード セット。 どちらの場合は、新しいレコード セットは、データ ソースの現在の状態を表します。  
  
 例については、次を参照してください。[レコード ビュー: セカンド レコード セットからリスト ボックス](../../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)です。  
  
> [!TIP]
>  最適化するために**Requery**パフォーマンス、レコード セットが変更されないように[フィルター](../../data/odbc/recordset-filtering-records-odbc.md)または[並べ替え](../../data/odbc/recordset-sorting-records-odbc.md)です。 呼び出しの前に、パラメーター値のみを変更する**Requery**です。  
  
 場合、 **Requery**呼び出しは失敗、呼び出しを再試行することができます。 それ以外の場合、アプリケーションを正常に終了します。 呼び出し**Requery**または**開く**のさまざまな理由のいずれかが失敗する可能性があります。 おそらくネットワーク エラーが発生します。またはの呼び出し時に、既存のデータがリリースされた後、新しいデータを取得すると、前に別のユーザー可能性があります get 排他的アクセスまたは、レコード セットが依存しているテーブルを削除できませんできます。  
  
## <a name="see-also"></a>関連項目  
 [レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)   
 [レコード セット: 動的に結びつける方法 (ODBC) のデータ列](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)   
 [レコードセット: レコードセットの生成と破棄 (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)