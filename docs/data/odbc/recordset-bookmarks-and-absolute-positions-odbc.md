---
title: 'レコード セット: ブックマークと絶対位置 (ODBC) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
f1_keywords:
- SetAbsolutePosition
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e5e45d2f9dd942e76ccce4231e8280a142e66e56
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33091318"
---
# <a name="recordset-bookmarks-and-absolute-positions-odbc"></a>レコードセット: ブックマークと絶対位置 (ODBC)
このトピックの内容は、MFC ODBC クラスに該当します。  
  
 レコード セット内を移動するときは、多くの場合、特定のレコードに戻る必要があります。 レコードのブックマークと絶対位置は、このような 2 つのメソッドを提供します。  
  
 このトピックでは、次の内容について説明します。  
  
-   [ブックマークの使用方法](#_core_bookmarks_in_mfc_odbc)です。  
  
-   [絶対位置を使用して現在のレコードを設定する方法](#_core_absolute_positions_in_mfc_odbc)です。  
  
##  <a name="_core_bookmarks_in_mfc_odbc"></a> MFC ODBC 内のブックマーク  
 ブックマークは、レコードを一意に識別します。 レコード セット内を移動するときに常に依存できない絶対位置をレコードのレコード セットからレコードを削除できるためです。 レコードの位置を追跡する信頼性の高い方法は、そのブックマークを使用します。 クラス`CRecordset`メンバー関数を提供します。  
  
-   変数に保存できるように現在のレコードのブックマークの取得 ([GetBookmark](../../mfc/reference/crecordset-class.md#getbookmark))。  
  
-   そのブックマークは、前の変数で保存するを指定することによって、特定のレコードにすばやく移動 ([SetBookmark](../../mfc/reference/crecordset-class.md#setbookmark))。  
  
 次の例では、これらのメンバー関数を使用して、現在のレコードをマークし、後で戻すことにする方法を示します。  
  
```  
// rs is a CRecordset or  
// CRecordset-derived object  
  
CDBVariant varRecordToReturnTo;  
rs.GetBookmark( varRecordToReturnTo );  
  
// More code in which you  
// move to other records  
  
rs.SetBookmark( varRecordToReturnTo );  
```  
  
 基になるデータ型を抽出する必要はありません、 [CDBVariant クラス](../../mfc/reference/cdbvariant-class.md)オブジェクト。 値を割り当てる`GetBookmark`にそのブックマークに戻ると`SetBookmark`です。  
  
> [!NOTE]
>  ODBC ドライバーとレコード セットの種類に応じてブックマークはサポートされません。 ブックマークは呼び出すことによってサポートされているかどうかを容易に判別[値](../../mfc/reference/crecordset-class.md#canbookmark)です。 さらに、ブックマークはサポートされている場合を明示的に選択してくださいを指定することによって機能を実装、 **crecordset::usebookmarks**オプション、 [:open](../../mfc/reference/crecordset-class.md#open)メンバー関数。 レコード セットの特定の操作の後、ブックマークの永続性を確認することも必要があります。 たとえば場合、する**Requery** 、レコード セットのブックマークが無効になります。 呼び出す[CDatabase::GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence)を安全に呼び出すことができるかどうかを確認する`SetBookmark`です。  
  
##  <a name="_core_absolute_positions_in_mfc_odbc"></a> MFC ODBC の絶対位置  
 クラスのブックマークのほか`CRecordset`序数の位置を指定して現在のレコードを設定することができます。 これには、絶対位置は呼び出されます。  
  
> [!NOTE]
>  絶対位置指定では、順方向専用レコード セットで使用できません。 前方スクロール専用レコードの詳細については、次を参照してください。[レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)です。  
  
 絶対位置を使用して現在のレコード ポインターを移動するには、呼び出す[CRecordset::SetAbsolutePosition](../../mfc/reference/crecordset-class.md#setabsoluteposition)です。 値を渡す場合`SetAbsolutePosition`、その序数位置が、現在のレコードに対応するレコード。  
  
> [!NOTE]
>  レコードの絶対位置では、信頼性の高い可能性があります。 レコード セットからレコードが削除されると、それ以降のレコードの序数位置が変更されます。 ブックマークは、現在のレコードを移動するための推奨される方法です。 詳細については、次を参照してください。 [MFC ODBC 内のブックマーク](#_core_bookmarks_in_mfc_odbc)です。  
  
 レコード セットの移動の詳細については、次を参照してください。[レコード セット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)です。  
  
## <a name="see-also"></a>関連項目  
 [レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)