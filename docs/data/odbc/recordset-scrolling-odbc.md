---
title: 'レコード セット: スクロール (ODBC) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 19058ec3d9a7840fc0e90be84f2734c49f2c8e85
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096208"
---
# <a name="recordset-scrolling-odbc"></a>レコードセット: スクロール (ODBC)
このトピックの内容は、MFC ODBC クラスに該当します。  
  
 レコード セットを開いた後と必要とする値を表示するレコードにアクセスする計算を実行、レポートを生成したりなどです。 スクロールのセット内のレコード間を移動できます。  
  
 このトピックでは、次の内容について説明します。  
  
-   [レコード セット内に 1 つのレコードのスクロール方法](#_core_scrolling_from_one_record_to_another)です。  
  
-   [スクロールの状況を通知し、サポートされていません ](#_core_when_scrolling_is_supported)です。  
  
##  <a name="_core_scrolling_from_one_record_to_another"></a> 別の 1 つのレコードからスクロール  
 クラス`CRecordset`提供、**移動**レコード セット内のスクロールのためのメンバー関数。 これらの関数は、行セットによって、現在のレコードを移動します。 バルク行フェッチを実装している場合、**移動**操作は、行セットのサイズによって、レコード セットを再配置します。 バルク行フェッチへの呼び出しを実装していない場合、**移動**関数が再配置レコード セットによって 1 つのレコードごとにします。 バルク行フェッチの詳細については、次を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)です。  
  
> [!NOTE]
>  レコード セット内を移動する場合、削除されたレコードがスキップされないことができます。 詳細については、次を参照してください。、 [IsDeleted](../../mfc/reference/crecordset-class.md#isdeleted)メンバー関数。  
  
 加え、**移動**関数、`CRecordset`レコード セットの先頭または末尾を越えたスクロールしたかどうかをチェックするためのメンバー関数を提供します。  
  
 スクロールがレコード セットに考えられるかどうかを判断するのには、呼び出し、`CanScroll`メンバー関数。  
  
#### <a name="to-scroll"></a>スクロールするには  
  
1.  1 つのレコードまたは 1 つの行セットを転送: 呼び出し、 [MoveNext](../../mfc/reference/crecordset-class.md#movenext)メンバー関数。  
  
2.  旧バージョンとの 1 つのレコードまたは 1 つの行セット: 呼び出し、 [MovePrev](../../mfc/reference/crecordset-class.md#moveprev)メンバー関数。  
  
3.  レコード セットの最初のレコードを: 呼び出し、 [MoveFirst](../../mfc/reference/crecordset-class.md#movefirst)メンバー関数。  
  
4.  レコード セットの最後のレコードと最後の行セット: 呼び出し、 [MoveLast](../../mfc/reference/crecordset-class.md#movelast)メンバー関数。  
  
5.  *N*現在の位置に対してレコード: 呼び出し、[移動](../../mfc/reference/crecordset-class.md#move)メンバー関数。  
  
#### <a name="to-test-for-the-end-or-the-beginning-of-the-recordset"></a>レコード セットの最初または終わりをテストするには  
  
1.  最後のレコードまでスクロールしたしますか。 呼び出す、 [IsEOF](../../mfc/reference/crecordset-class.md#iseof)メンバー関数。  
  
2.  (逆方向に移動する)、最初のレコードをスクロールしたしますか。 呼び出す、 [IsBOF](../../mfc/reference/crecordset-class.md#isbof)メンバー関数。  
  
 次のコード例では`IsBOF`と`IsEOF`どちらの方向にスクロールする場合は、レコード セットの制限を検出するためにします。  
  
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
  
 `IsEOF` 過去の最後のレコードは、レコード セットが配置されている場合は、0 以外の値を返します。 `IsBOF` レコード セットが (すべてのレコード) の前に、最初のレコードの前に配置されている場合は、0 以外の値を返します。 どちらの場合は、操作するために現在のレコードはありません。 呼び出す場合`MovePrev`とき`IsBOF`は既に**TRUE**呼び出しまたは`MoveNext`ときに`IsEOF`は既に**TRUE**がスローされます、`CDBException`です。 使用することも`IsBOF`と`IsEOF`空のレコード セットを確認します。  
  
 レコード セットの移動の詳細については、次を参照してください。[レコード セット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)です。  
  
##  <a name="_core_when_scrolling_is_supported"></a> スクロールがサポートされている場合  
 最初にデザインされたとして SQL では、前方スクロールのみ、指定されたが、ODBC がスクロール機能を拡張できます。 スクロールするためのサポートの利用可能なレベルは、アプリケーションは、ドライバーの ODBC API への準拠レベルで動作する ODBC ドライバーに依存し、ODBC カーソル ライブラリがメモリに読み込まれるかどうか。 詳細については、次を参照してください。 [ODBC](../../data/odbc/odbc-basics.md)と[ODBC: ODBC カーソル ライブラリ](../../data/odbc/odbc-the-odbc-cursor-library.md)です。  
  
> [!TIP]
>  カーソル ライブラリを使用するかどうかを制御できます。 参照してください、`bUseCursorLib`と`dwOptions`パラメーター [cdatabase::open](../../mfc/reference/cdatabase-class.md#open)です。  
  
> [!NOTE]
>  MFC DAO クラスとは異なり、MFC ODBC クラスに渡さないように一連の**検索**条件を満たす次 (または前) のレコードを検索するために機能します。  
  
## <a name="see-also"></a>関連項目  
 [レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)   
 [CRecordset::CanScroll](../../mfc/reference/crecordset-class.md#canscroll)   
 [CRecordset::CheckRowsetError](../../mfc/reference/crecordset-class.md#checkrowseterror)   
 [レコードセット: レコードのフィルター処理 (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)