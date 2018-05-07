---
title: 'レコード フィールド エクス チェンジ: RFX 関数の使用 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC [C++], data types
- data types [C++], ODBC record field exchange
- RFX (ODBC) [C++], function syntax and parameters
- DoFieldExchange method, and RFX functions
- ODBC [C++], RFX
- RFX (ODBC) [C++], data types
- function calls, RFX functions
ms.assetid: c594300b-5a29-4119-a68b-e7ca32def696
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1f834f9f52c8d01dbd7eb3ff54b794afc11630ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="record-field-exchange-using-the-rfx-functions"></a>レコード フィールド エクスチェンジ: RFX 関数の使い方
このトピックの本文を構成する RFX 関数の呼び出しを使用する方法について説明、`DoFieldExchange`をオーバーライドします。  
  
> [!NOTE]
>  このトピックの対象から派生したクラス[CRecordset](../../mfc/reference/crecordset-class.md)バルク行フェッチは実装されていません。 バルク行フェッチを使用している場合は、バルク レコード フィールド エクス チェンジ (Bulk RFX) が実装されます。 バルク rfx 関数は rfx 関数に似ています。 相違点を理解するのを参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)です。  
  
 RFX のグローバル関数は、データ ソースとフィールド データ メンバーで、レコード セット内の列の間でデータを交換します。 レコード セットの RFX 関数を記述する[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)メンバー関数。 このトピックでは、関数を簡単に説明し、どの rfx 関数は、使用可能なデータ型を示します。 [テクニカル ノート 43](../../mfc/tn043-rfx-routines.md)追加のデータ型の RFX 関数を記述する方法について説明します。  
  
##  <a name="_core_rfx_function_syntax"></a> RFX 関数の構文  
 各 RFX 関数は 3 つのパラメーターを受け取ります (および、省略可能な 4 番目または 5 番目のパラメーターを受け取る一部)。  
  
-   ポインター、 [CFieldExchange](../../mfc/reference/cfieldexchange-class.md)オブジェクト。 に沿って渡します、`pFX`にポインターを渡す`DoFieldExchange`です。  
  
-   データ ソースに列の名前が表示されます。  
  
-   対応するフィールド データ メンバーまたはレコード セット クラス内のパラメーターのデータ メンバーの名前。  
  
-   (省略可能)で、関数、文字列または配列を転送中の最大長の一部です。 既定値は 255 (バイト単位) が、これを変更する可能性があります。 最大サイズはの最大サイズに基づいて、`CString`オブジェクト- **INT_MAX** (2,147, 483,647) バイト-サイズにする前にドライバーの制限が発生する可能性がありますが、します。  
  
-   (省略可能)`RFX_Text`関数、ことがありますパラメーターを使用する 5 番目の列のデータ型を指定します。  
  
 詳細については、下にある RFX 関数を参照してください。[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)で、*クラス ライブラリ リファレンス*です。 特殊な使い方の例については、パラメーターの使用を参照してください[レコード セット: 集計およびその他の集計計算 (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)です。  
  
##  <a name="_core_rfx_data_types"></a> RFX データ型  
 クラス ライブラリには、データ ソースとレコード セットの間で多数の異なるデータ型を転送するための RFX 関数が用意されています。 次の一覧には、データ型での RFX 関数の概要を示します。 RFX 関数呼び出しを記述する必要がありますの場合、データ型でこれらの関数から選択します。  
  
|関数|データの種類|  
|--------------|---------------|  
|`RFX_Bool`|**BOOL**|  
|`RFX_Byte`|**BYTE**|  
|`RFX_Binary`|`CByteArray`|  
|`RFX_Double`|**double**|  
|`RFX_Single`|**float**|  
|`RFX_Int`|`int`|  
|`RFX_Long`|**long**|  
|`RFX_LongBinary`|`CLongBinary`|  
|`RFX_Text`|`CString`|  
|`RFX_Date`|`CTime`|  
  

 詳細については、マニュアルを参照して、RFX 関数 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)で、*クラス ライブラリ リファレンス*です。 C++ のデータ型が SQL データ型にマップする方法については、ANSI SQL データ型にマップ C++ のデータ型の表を参照してください。  [SQL: SQL と C++ のデータ型 (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)です。  
  
## <a name="see-also"></a>関連項目  
 [レコード フィールド エクス (チェンジ RFX)](../../data/odbc/record-field-exchange-rfx.md)   
 [レコード フィールド エクス チェンジ: RFX の動作方法](../../data/odbc/record-field-exchange-how-rfx-works.md)   
 [レコード セット: レコード セット (ODBC) のパラメーター化](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)   
 [レコード セット: 動的に結びつける方法 (ODBC) のデータ列](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)   
 [CRecordset クラス](../../mfc/reference/crecordset-class.md)   
 [CFieldExchange クラス](../../mfc/reference/cfieldexchange-class.md)