---
description: '詳細情報: レコードセット: スクロール (ODBC)'
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
ms.openlocfilehash: 82a4326f2e0a7546d956181e7660ea0f1a437dc6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204460"
---
# <a name="recordset-scrolling-odbc"></a>レコードセット: スクロール (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

レコードセットを開いた後は、レコードにアクセスして、値の表示、計算の実行、レポートの生成などを行う必要があります。 スクロールを使用すると、レコードをレコードセット内のレコードに移動できます。

このトピックでは、次の内容について説明します。

- レコード[セット内のあるレコードから別のレコードにスクロールする方法](#_core_scrolling_from_one_record_to_another)。

- [どのような状況でスクロールするかはサポートされていません](#_core_when_scrolling_is_supported)。

## <a name="scrolling-from-one-record-to-another"></a><a name="_core_scrolling_from_one_record_to_another"></a> スクロール (1 つのレコードから別のレコードに)

クラス `CRecordset` は、 `Move` レコードセット内をスクロールするためのメンバー関数を提供します。 これらの関数は、現在のレコードを行セット別に移動します。 バルク行フェッチを実装している場合、 `Move` 操作は行セットのサイズでレコードセットを再配置します。 バルク行フェッチを実装していない場合、関数を呼び出すと、 `Move` 毎回レコードセットが1つのレコードによって再配置されます。 バルク行フェッチの詳細については、「レコード [セット: バルクデータフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

> [!NOTE]
> レコードセットを移動するときに、削除されたレコードがスキップされないことがあります。 詳細については、「 [IsDeleted](../../mfc/reference/crecordset-class.md#isdeleted) メンバー関数」を参照してください。

関数に加えて `Move` 、には、 `CRecordset` レコードセットの先頭から末尾までの間にスクロールしたかどうかを確認するためのメンバー関数が用意されています。

レコードセットでスクロールできるかどうかを判断するには、 `CanScroll` メンバー関数を呼び出します。

#### <a name="to-scroll"></a>スクロールするには

1. 1つのレコードまたは1つの行セットを転送する: [MoveNext](../../mfc/reference/crecordset-class.md#movenext) メンバー関数を呼び出します。

1. 1つ以上のレコードまたは1つの行セット: [MovePrev](../../mfc/reference/crecordset-class.md#moveprev) メンバー関数を呼び出します。

1. レコードセットの最初のレコードに対しては、 [MoveFirst](../../mfc/reference/crecordset-class.md#movefirst) メンバー関数を呼び出します。

1. レコードセットの最後のレコード、または最後の行セットに対しては、 [MoveLast](../../mfc/reference/crecordset-class.md#movelast) メンバー関数を呼び出します。

1. 現在の位置を基準とした *N* レコード:[移動](../../mfc/reference/crecordset-class.md#move)メンバー関数を呼び出します。

#### <a name="to-test-for-the-end-or-the-beginning-of-the-recordset"></a>レコードセットの末尾または先頭をテストするには

1. 最後のレコードを超えてスクロールしたか。 [IsEOF](../../mfc/reference/crecordset-class.md#iseof)メンバー関数を呼び出します。

1. 最初のレコードの前にスクロールしたことがありますか (後方に移動)。 [IsBOF](../../mfc/reference/crecordset-class.md#isbof)メンバー関数を呼び出します。

次のコード例では、とを使用 `IsBOF` して、 `IsEOF` いずれかの方向にスクロールするときにレコードセットの制限を検出します。

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

`IsEOF` レコードセットが最後のレコードの後に配置されている場合、は0以外の値を返します。 `IsBOF` レコードセットが最初のレコード (すべてのレコードの前) の前に配置されている場合、は0以外の値を返します。 どちらの場合も、操作する現在のレコードは存在しません。 `MovePrev` `IsBOF` が既に true である場合、またはが既に true の場合にを呼び出すと、 `MoveNext` `IsEOF` フレームワークはをスローし `CDBException` ます。 およびを使用して、 `IsBOF` `IsEOF` 空のレコードセットを確認することもできます。

レコードセットナビゲーションの詳細については、「 [レコードセット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)」を参照してください。

## <a name="when-scrolling-is-supported"></a><a name="_core_when_scrolling_is_supported"></a> スクロールがサポートされている場合

当初は、SQL では前方スクロールのみが提供されていましたが、ODBC はスクロール機能を拡張しています。 スクロールのサポートレベルは、アプリケーションが使用する ODBC ドライバー、ドライバーの ODBC API の準拠レベル、および ODBC カーソルライブラリがメモリに読み込まれるかどうかによって異なります。 詳細については、「odbc および[odbc: Odbc カーソルライブラリ](../../data/odbc/odbc-the-odbc-cursor-library.md)」を[参照して](../../data/odbc/odbc-basics.md)ください。

> [!TIP]
> カーソルライブラリを使用するかどうかを制御できます。 「 *BUseCursorLib* and *DwOptions* parameters To [CDatabase:: Open](../../mfc/reference/cdatabase-class.md#open)」を参照してください。

> [!NOTE]
> MFC DAO クラスとは異なり、MFC ODBC クラスには、 `Find` 指定された条件を満たす次 (または前) のレコードを検索するための一連の関数が用意されていません。

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[CRecordset:: CanScroll](../../mfc/reference/crecordset-class.md#canscroll)<br/>
[CRecordset:: CheckRowsetError](../../mfc/reference/crecordset-class.md#checkrowseterror)<br/>
[レコードセット: レコードのフィルター処理 (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)
