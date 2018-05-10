---
title: 'レコード セット: 大量のデータ項目 (ODBC) の操作 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- BLOB (binary large object), recordsets
- ODBC recordsets, binary large objects
- recordsets, binary large objects
- binary large objects
- CLongBinary class, using in recordsets
ms.assetid: 3e80b5a8-b6e7-43c6-a816-e54befc513a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6845d2e3c1b1eac31486200a0f610037d4774626
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="recordset-working-with-large-data-items-odbc"></a>レコードセット: 大量のデータの処理 (ODBC)
このトピックは、MFC ODBC クラスと MFC DAO クラスの両方に適用されます。  
  
> [!NOTE]
>  MFC DAO クラスを使用している場合は、クラス、大量のデータ項目を管理[CByteArray](../../mfc/reference/cbytearray-class.md)クラスではなく[CLongBinary](../../mfc/reference/clongbinary-class.md)です。 MFC ODBC クラスにバルク行フェッチを使用している場合を使用して`CLongBinary`なく`CByteArray`です。 バルク行フェッチの詳細については、次を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)です。  
  
 たとえば、データベースは、ビットマップ (従業員の写真、マップ、製品や OLE オブジェクトの画像) などのデータの大きなデータを格納できるとします。 このようなデータが呼ばバイナリ ラージ オブジェクト (BLOB) としてため。  
  
-   各フィールドの値は、大規模なです。  
  
-   番号とその他の単純なデータ型とは異なりがない予測可能なサイズ。  
  
-   データは、プログラムの観点から formless です。  
  
 このトピックでは、このようなオブジェクトを操作するためにデータベース クラスが用意されているどのようなサポートについて説明します。  
  
##  <a name="_core_managing_large_objects"></a> ラージ オブジェクトを管理します。  
 レコード セットには、バイナリ ラージ オブジェクトを管理するための特別な問題を解決するために 2 つの方法があります。 クラスを使用して[CByteArray](../../mfc/reference/cbytearray-class.md)クラスを使用することも[CLongBinary](../../mfc/reference/clongbinary-class.md)です。 一般に、`CByteArray`は、大きなバイナリ データを管理することをお勧めします。  
  
 `CByteArray` 以上のオーバーヘッドを必要と`CLongBinary`がより高機能な」の説明に従って[CByteArray クラス](#_core_the_cbytearray_class)です。 `CLongBinary` 簡単な説明[CLongBinary クラス](#_core_the_clongbinary_class)です。  
  
 詳細についてを使用して`CByteArray`大量のデータ項目を操作するを参照してください。[テクニカル ノート 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md)です。  
  
##  <a name="_core_the_cbytearray_class"></a> CByteArray クラス  
 `CByteArray` MFC コレクション クラスの 1 つです。 A`CByteArray`オブジェクトはバイトの動的配列を格納、必要に応じて、配列は拡張できます。 クラスは、組み込みの C++ 配列の場合と、インデックスによる高速アクセスを提供します。 `CByteArray` オブジェクトをシリアル化され、診断用にダンプすることができます。 クラスは、取得し指定したバイト数を設定、挿入し (バイト単位) を追加および 1 バイトまたはすべてのバイトを削除するためのメンバー関数を提供します。 これらの機能によって、簡単にバイナリ データを解析します。 たとえば、バイナリのオブジェクトが OLE オブジェクトの場合は、実際のオブジェクトに到達するいくつかのヘッダー バイトを使用する必要があります。  
  
##  <a name="_core_using_cbytearray_in_recordsets"></a> レコード セットで CByteArray の使用  
 レコード セットのフィールド データ メンバーに型を提供することにより`CByteArray`、元の固定ベースを提供する[RFX](../../data/odbc/record-field-exchange-rfx.md)とのレコード セットと、データ ソースの間で操作できるようなオブジェクトの転送を管理できる、オブジェクト内のデータです。 RFX、取得したデータの特定のサイトを必要があり、基になるデータにアクセスする必要があります。  
  
 詳細についてを使用して`CByteArray`大量のデータ項目を操作するを参照してください。[テクニカル ノート 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md)です。  
  
##  <a name="_core_the_clongbinary_class"></a> CLongBinary クラス  
 A [CLongBinary](../../mfc/reference/clongbinary-class.md)オブジェクトは、単純なシェルの周り、`HGLOBAL`ヒープに割り当てられた記憶域のブロックを処理します。 RFX を割り当てます、バイナリ ラージ オブジェクトを含むテーブル列をバインドされているときに、`HGLOBAL`レコード セットにデータを転送する必要がありますでのハンドルを格納するときに処理、`CLongBinary`レコード セットのフィールドです。  
  
 さらを使用する、`HGLOBAL`処理、 `m_hData`、操作のいずれかの処理とデータ自体には、データを操作します。 ここでは[CByteArray](../../mfc/reference/cbytearray-class.md)機能を追加します。  
  
> [!CAUTION]
>  CLongBinary オブジェクトは、関数呼び出しでパラメーターとして使用できません。 さらに、その実装は、呼び出す **:: SQLGetData**、必ずしも、スクロール可能なスナップショットのスクロールのパフォーマンスが低下します。 可能性もある場合は true を使用するときに、 **:: SQLGetData**動的スキーマの列を取得するために直接できます。  
  
## <a name="see-also"></a>関連項目  
 [レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)   
 [レコード セット: 合計およびその他の集計の結果 (ODBC) を取得します。](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)   
 [レコード フィールド エクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)