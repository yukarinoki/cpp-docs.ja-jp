---
title: 'レコードセット: ブックマークと絶対位置 (ODBC)'
ms.date: 11/04/2016
f1_keywords:
- SetAbsolutePosition
helpviewer_keywords:
- CDBVariant class, bookmarks
- absolute positions, ODBC recordsets
- bookmarks, CDBVariant
- bookmarks, ODBC recordsets
- ODBC recordsets, absolute positions
- ODBC recordsets, bookmarks
- cursors [ODBC], absolute position in recordsets
- recordsets, bookmarks
- bookmarks
- SetAbsolutePosition method
- recordsets, absolute positions
- positioning records
- SetBookmark method
- record positioning
- GetBookmark method
- SetAbsolutePosition method, bookmarks
ms.assetid: 189788d6-33c1-41c5-9265-97db2a5d43cc
ms.openlocfilehash: 77c8bbaf7c0bc21dab62c3785364e72656287815
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367065"
---
# <a name="recordset-bookmarks-and-absolute-positions-odbc"></a>レコードセット: ブックマークと絶対位置 (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

レコードセット内を移動する場合、特定のレコードに戻る方法が必要な場合があります。 レコードのブックマークと絶対位置は、このような 2 つのメソッドを提供します。

このトピックでは、次の内容について説明します。

- [ブックマークの使用方法](#_core_bookmarks_in_mfc_odbc)

- [絶対位置を使用して現在のレコードを設定する方法](#_core_absolute_positions_in_mfc_odbc).

## <a name="bookmarks-in-mfc-odbc"></a><a name="_core_bookmarks_in_mfc_odbc"></a>MFC ODBC のブックマーク

ブックマークはレコードを一意に識別します。 レコードセット内を移動する場合、レコードはレコードセットから削除できるため、レコードの絶対位置に常に依存できません。 レコードの位置を追跡する信頼できる方法は、そのブックマークを使用することです。 クラス`CRecordset`には、次のメンバ関数が用意されています。

- 現在のレコードのブックマークを取得するため、変数 ([GetBookmark](../../mfc/reference/crecordset-class.md#getbookmark)) に保存できます。

- 前の変数 ([SetBookmark](../../mfc/reference/crecordset-class.md#setbookmark)) に保存したブックマークを指定して、特定のレコードにすばやく移動します。

次の例は、これらのメンバー関数を使用して現在のレコードをマークし、後でレコードに戻る方法を示しています。

```cpp
// rs is a CRecordset or
// CRecordset-derived object

CDBVariant varRecordToReturnTo;
rs.GetBookmark( varRecordToReturnTo );

// More code in which you
// move to other records

rs.SetBookmark( varRecordToReturnTo );
```

基になるデータ型を[CDBVariant クラス](../../mfc/reference/cdbvariant-class.md)オブジェクトから抽出する必要はありません。 で`GetBookmark`値を割り当て、そのブックマーク`SetBookmark`に戻ります。

> [!NOTE]
> ODBC ドライバおよびレコードセットの種類によっては、ブックマークがサポートされていない場合があります。 ブックマークがサポートされているかどうかを簡単に判断するには[、CRecordset::CanBookmark](../../mfc/reference/crecordset-class.md#canbookmark)を呼び出します。 さらに、ブックマークがサポートされている場合は[、CRecordset::Open](../../mfc/reference/crecordset-class.md#open)メンバー関数でオプションを`CRecordset::useBookmarks`指定して、ブックマークを明示的に実装することを選択する必要があります。 また、特定のレコードセット操作の後にブックマークの永続化を確認する必要があります。 たとえば、レコードセットの`Requery`場合、ブックマークが無効になる可能性があります。 [を](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence)呼び出して、安全に呼び出`SetBookmark`すことができるかどうかを確認します。

## <a name="absolute-positions-in-mfc-odbc"></a><a name="_core_absolute_positions_in_mfc_odbc"></a>MFC ODBC の絶対位置

ブックマーク以外にも、クラス`CRecordset`では、序数の位置を指定して現在のレコードを設定できます。 これは絶対位置決めと呼ばれます。

> [!NOTE]
> 絶対位置指定は、前方のレコードセットでは使用できません。 転送専用レコードセットの詳細については、「[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)」を参照してください。

絶対位置を使用して現在のレコード ポインタを移動するには[、CRecordset::セット絶対位置](../../mfc/reference/crecordset-class.md#setabsoluteposition)を呼び出します。 に`SetAbsolutePosition`値を渡すと、その序数位置に対応するレコードがカレント レコードになります。

> [!NOTE]
> レコードの絶対位置は、信頼できない可能性があります。 ユーザーがレコードセットからレコードを削除すると、後続のレコードの位置が変更されます。 ブックマークは、現在のレコードを移動する場合に推奨される方法です。 詳細については[、「MFC ODBC でのブックマーク](#_core_bookmarks_in_mfc_odbc)」を参照してください。

レコードセットのナビゲーションの詳細については、「[レコードセット : スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)
