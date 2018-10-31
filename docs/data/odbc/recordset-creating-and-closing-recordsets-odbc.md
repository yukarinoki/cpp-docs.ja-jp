---
title: 'レコード セット: を作成するレコード セットと破棄 (ODBC) |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets, creating
- recordsets, creating
- recordsets, opening
- recordsets, closing
- ODBC recordsets, closing
- ODBC recordsets, opening
ms.assetid: 8d2aac23-4396-4ce2-8c60-5ecf1b360d3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4da86f43cf89720132aba0eaa611a01a3902fb1a
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059026"
---
# <a name="recordset-creating-and-closing-recordsets-odbc"></a>レコードセット: レコードセットの生成と破棄 (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

レコード セットを使用するレコード セット オブジェクトの構築を呼び出してその`Open`メンバー関数は、レコード セットのクエリを実行し、レコードを選択します。 レコード セットが完了したらと閉じるオブジェクトを破棄します。

このトピックでは、次の内容について説明します。

- [レコード セット オブジェクトを作成するタイミングと方法](#_core_creating_recordsets_at_run_time)します。

- [タイミングと方法は、パラメーター化、フィルター処理、並べ替え、またはロックによって、レコード セットの動作を修飾することができます](#_core_setting_recordset_options)します。

- [レコード セット オブジェクトを終了するタイミングと方法](#_core_closing_a_recordset)します。

##  <a name="_core_creating_recordsets_at_run_time"></a> 実行時にレコード セットの作成

レコード セット オブジェクトを作成するには、プログラムで、前に、アプリケーション固有のレコード セット クラスを通常記述します。 この手順の詳細については、次を参照してください。 [MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)します。

データ ソースからレコードを選択する必要がある場合は、ダイナセットまたはスナップショットのオブジェクトを開きます。 作成するオブジェクトの型が行う必要がある依存データ、アプリケーションで、どのような ODBC ドライバーをサポートするいるとします。 詳細については、次を参照してください。[ダイナセット](../../data/odbc/dynaset.md)と[スナップショット](../../data/odbc/snapshot.md)します。

#### <a name="to-open-a-recordset"></a>レコード セットを開く

1. オブジェクトを構築、 `CRecordset`-クラスを派生します。

   ヒープまたは関数のスタック フレーム オブジェクトを構築することができます。

1. 必要に応じて既定のレコード セットの動作を変更します。 使用可能なオプションで、次を参照してください。[レコード セットのオプションの設定](#_core_setting_recordset_options)します。

1. オブジェクトの[オープン](../../mfc/reference/crecordset-class.md#open)メンバー関数。

コンス トラクターへのポインターを渡す、`CDatabase`オブジェクトまたはされによって返される接続文字列に基づくフレームワークを構築する一時的なデータベース オブジェクトを使用して NULL を渡す、 [GetDefaultConnect](../../mfc/reference/crecordset-class.md#getdefaultconnect)メンバー関数。 `CDatabase`オブジェクトは、データ ソースに既に接続可能性があります。

呼び出し`Open`SQL を使用して、データ ソースからレコードを選択します。 (ある場合) を選択した最初のレコードは、現在のレコードです。 このレコードのフィールドの値は、レコード セット オブジェクトのフィールド データ メンバーに格納されます。 すべてのレコードが選択されて場合、両方の`IsBOF`と`IsEOF`メンバー関数は 0 を返します。

[オープン](../../mfc/reference/crecordset-class.md#open)呼び出しができます。

- レコード セットがダイナセットまたはスナップショットであるかどうかを指定します。 レコード セットは、既定では、スナップショットとして開きます。 または、前方スクロール、順方向専用のレコードを指定することができます。

   既定では、レコード セットに格納されている既定の種類を使用して、`CRecordset`データ メンバー`m_nDefaultType`します。 ウィザードを初期化するコードを記述する`m_nDefaultType`ウィザードで選択したレコード セットの種類にします。 この既定を受け入れるのではなく、別のレコード セットの種類を置き換えることができます。

- 既定の SQL を置換する文字列を指定**選択**レコード セットを作成するステートメント。

- レコード セットが読み取り専用、または追加専用であるかどうかを指定します。 既定では、レコード セットを許可するが、されるを制限するには新しいレコードのみを追加するまたはすべての更新プログラムを無効にすることができます。

次の例は、クラスの読み取り専用スナップショットのオブジェクトを開く方法を示しています。`CStudentSet`を、アプリケーション固有のクラス。

```cpp
// Construct the snapshot object
CStudentSet rsStudent( NULL );
// Set options if desired, then open the recordset
if(!rsStudent.Open(CRecordset::snapshot, NULL, CRecordset::readOnly))
    return FALSE;
// Use the snapshot to operate on its records...
```

呼び出した後`Open`オブジェクトのメンバー関数とデータ メンバーを使用してレコードを処理します。 場合によっては、クエリを再実行またはデータ ソースで発生した変更を含めるレコード セットを更新する可能性があります。 詳細については、次を参照してください。[レコード セット: レコード セット (ODBC) のクエリを再実行](../../data/odbc/recordset-requerying-a-recordset-odbc.md)します。

> [!TIP]
>  開発時に使用する接続文字列では、最終的なユーザーが必要な接続文字列は指定できません可能性があります。 この点で、アプリケーションを汎用化する方法については、次を参照してください。[データ ソース: 接続 (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)します。

##  <a name="_core_setting_recordset_options"></a> レコード セットのオプションの設定

レコード セット オブジェクトの構築後を呼び出す前に、`Open`レコードを選択するをレコード セットの動作を制御するいくつかのオプションを設定することがあります。 すべてのレコード セットの次の操作を実行できます。

- 指定、[フィルター](../../data/odbc/recordset-filtering-records-odbc.md)レコードの選択を制限します。

- 指定、[並べ替え](../../data/odbc/recordset-sorting-records-odbc.md)レコードの順序。

- 指定[パラメーター](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)情報を取得または実行時に計算を使用してレコードを選択できるようにします。

条件を満たす場合、次のオプションを設定することもできます。

- レコード セットは更新可能であり、ロック オプションをサポートする場合は、指定、[ロック](../../data/odbc/recordset-locking-records-odbc.md)メソッドの更新に使用します。

> [!NOTE]
>  レコードの選択に影響を与える、呼び出す前に、これらのオプションを設定する必要があります、`Open`メンバー関数。

##  <a name="_core_closing_a_recordset"></a> レコード セットを閉じる

レコード セットが完了したら、ときに、破棄し、そのメモリの割り当てを解除する必要があります。

#### <a name="to-close-a-recordset"></a>レコード セットを閉じる

1. 呼び出すその[閉じる](../../mfc/reference/crecordset-class.md#close)メンバー関数。

1. レコード セット オブジェクトを破棄します。

   関数のスタック フレームで宣言したとき、オブジェクトがスコープから外れたときに、オブジェクトに自動的に破棄されます。 それ以外の場合、使用、**削除**演算子。

`Close` レコード セットの解放`HSTMT`を処理します。 C++ のオブジェクトは破棄されません。

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)<br/>
[レコードセット: レコードの追加、更新、削除 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)