---
title: 'レコードセット: スクロール (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets [C++], end of
- recordsets [C++], beginning of
- navigation [C++], recordsets
- recordsets [C++], moving to records
- ODBC recordsets, scrolling
- recordsets [C++], navigating
- scrolling [C++], recordsets
- Move method (recordsets)
ms.assetid: f38d2dcb-1e88-4e41-af25-98b00c276be4
ms.openlocfilehash: 931051296dff495939fcbd894102a1b00e48ee90
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366941"
---
# <a name="recordset-scrolling-odbc"></a>レコードセット: スクロール (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

レコードセットを開いた後、レコードにアクセスして値の表示、計算、レポートの生成などを行う必要があります。 スクロールすると、レコードセット内のレコード間を移動できます。

このトピックでは、次の内容について説明します。

- [レコードセット内のレコードをスクロールする方法](#_core_scrolling_from_one_record_to_another)

- [どのような状況下でスクロールがサポートされていますが、サポートされていません](#_core_when_scrolling_is_supported)。

## <a name="scrolling-from-one-record-to-another"></a><a name="_core_scrolling_from_one_record_to_another"></a>あるレコードから別のレコードへのスクロール

クラス`CRecordset`は、`Move`レコードセット内をスクロールするためのメンバー関数を提供します。 これらの関数は、現在のレコードを行セットごとに移動します。 バルク行フェッチを実装している場合、操作は`Move`行セットのサイズでレコードセットを再配置します。 バルク行フェッチを実装していない場合、`Move`関数の呼び出しは、レコードセットを毎回 1 レコードずつ再配置します。 バルク行フェッチの詳細については、「[レコードセット : レコードの一括フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

> [!NOTE]
> レコードセット内を移動する場合、削除されたレコードはスキップされないことがあります。 詳細については[、IsDeleted](../../mfc/reference/crecordset-class.md#isdeleted)メンバー関数を参照してください。

関数に加えて`Move`、`CRecordset`レコードセットの末尾を越えてスクロールしたか、先頭よりも前にスクロールしたかどうかを確認するためのメンバー関数を提供します。

レコードセットでスクロールできるかどうかを確認するには、メンバー関数を`CanScroll`呼び出します。

#### <a name="to-scroll"></a>スクロールするには

1. 1 つのレコードまたは 1 つの行セットを転送する: [MoveNext](../../mfc/reference/crecordset-class.md#movenext)メンバー関数を呼び出します。

1. 1 つのレコードまたは 1 つの行セットを逆方向に戻す場合は[、MovePrev](../../mfc/reference/crecordset-class.md#moveprev)メンバー関数を呼び出します。

1. レコードセットの最初のレコードに対して、 [MoveFirst](../../mfc/reference/crecordset-class.md#movefirst)メンバー関数を呼び出します。

1. レコードセットの最後のレコードまたは最後の行セットに対して、 [MoveLast](../../mfc/reference/crecordset-class.md#movelast)メンバー関数を呼び出します。

1. 現在の位置に対する*相対 N*レコード: [Move](../../mfc/reference/crecordset-class.md#move)メンバー関数を呼び出します。

#### <a name="to-test-for-the-end-or-the-beginning-of-the-recordset"></a>レコードセットの末尾または先頭をテストするには

1. 最後のレコードをスクロールしましたか? [IsEOF](../../mfc/reference/crecordset-class.md#iseof)メンバー関数を呼び出します。

1. 最初のレコードの前にスクロールしましたか (後方へ移動) [メンバー](../../mfc/reference/crecordset-class.md#isbof)関数を呼び出します。

次のコード例では`IsBOF`、`IsEOF`どちらかの方向にスクロールするときにレコードセットの制限を使用し、検出します。

```
// Open a recordset; first record is current
CCustSet rsCustSet( NULL );
rsCustSet.Open( );

if( rsCustSet.IsBOF( ) )
    return;
    // The recordset is empty

// Scroll to the end of the recordset, past
// the last record, so no record is current
while ( !rsCustSet.IsEOF( ) )
    rsCustSet.MoveNext( );

// Move to the last record
rsCustSet.MoveLast( );

// Scroll to beginning of the recordset, before
// the first record, so no record is current
while( !rsCustSet.IsBOF( ) )
    rsCustSet.MovePrev( );

// First record is current again
rsCustSet.MoveFirst( );
```

`IsEOF`レコードセットが最後のレコードより後に配置されている場合は、0 以外の値を返します。 `IsBOF`レコードセットが最初のレコードの前 (すべてのレコードの前) にある場合は、0 以外の値を返します。 どちらの場合も、操作する現在のレコードはありません。 すでに TRUE `MovePrev` `IsBOF`のときに呼び出`MoveNext`すか`IsEOF`、既に TRUE の場合に`CDBException`呼び出すと、フレームワークは . また、空の`IsBOF`レコード`IsEOF`セットを使用してチェックすることもできます。

レコードセットのナビゲーションの詳細については、「[レコードセット : ブックマークと絶対位置 (ODBC)」](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)を参照してください。

## <a name="when-scrolling-is-supported"></a><a name="_core_when_scrolling_is_supported"></a>スクロールがサポートされている場合

当初の設計では、SQL は前方スクロールのみを提供していましたが、ODBC ではスクロール機能が拡張されています。 スクロールのサポートレベルは、アプリケーションで使用する ODBC ドライバー、ドライバーの ODBC API 準拠レベル、および ODBC カーソル ライブラリがメモリに読み込まれているかどうかによって異なります。 詳細については[、「ODBC](../../data/odbc/odbc-basics.md)および[ODBC: ODBC カーソル ライブラリ](../../data/odbc/odbc-the-odbc-cursor-library.md)」を参照してください。

> [!TIP]
> カーソル ライブラリを使用するかどうかを制御できます。 [「Cデータベース::オープン](../../mfc/reference/cdatabase-class.md#open)*」* の*パラメータ*を参照してください。

> [!NOTE]
> MFC DAO クラスとは異なり、MFC ODBC クラスには`Find`、指定した条件を満たす次の (または前の) レコードを検索するための関数のセットは用意されていません。

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット::缶詰](../../mfc/reference/crecordset-class.md#canscroll)<br/>
[エラーをチェックします。](../../mfc/reference/crecordset-class.md#checkrowseterror)<br/>
[レコードセット: レコードのフィルター処理 (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)
