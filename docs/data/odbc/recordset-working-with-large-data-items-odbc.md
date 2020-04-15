---
title: 'レコードセット: 大量のデータの処理 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- BLOB (binary large object), recordsets
- ODBC recordsets, binary large objects
- recordsets, binary large objects
- binary large objects
- CLongBinary class, using in recordsets
ms.assetid: 3e80b5a8-b6e7-43c6-a816-e54befc513a3
ms.openlocfilehash: 872fa7229738314b86b6ae6c0d5dc5a5562b27f1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360601"
---
# <a name="recordset-working-with-large-data-items-odbc"></a>レコードセット: 大量のデータの処理 (ODBC)

このトピックは、MFC ODBC クラスと MFC DAO クラスの両方に適用されます。

> [!NOTE]
> MFC DAO クラスを使用している場合は、クラス[CLongBinary](../../mfc/reference/clongbinary-class.md)ではなく[CByteArray](../../mfc/reference/cbytearray-class.md)クラスを使用して大きなデータ項目を管理します。 一括行フェッチで MFC ODBC クラスを使用する場合`CLongBinary`は、`CByteArray`ではなく を使用します。 バルク行フェッチの詳細については、「[レコードセット : レコードの一括フェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

データベースに、ビットマップ (従業員の写真、マップ、製品の画像、OLE オブジェクトなど) などの大きなデータを格納できるとします。 このようなデータは、バイナリ ラージ オブジェクト (BLOB) と呼ばれることが多いのは、次の理由からです。

- 各フィールド値は大きいです。

- 数値やその他の単純なデータ型とは異なり、予測可能なサイズはありません。

- データはプログラムの観点からは形式が無い。

このトピックでは、このようなオブジェクトを処理するためにデータベース クラスが提供するサポートについて説明します。

## <a name="managing-large-objects"></a><a name="_core_managing_large_objects"></a>ラージ オブジェクトの管理

レコードセットには、バイナリ ラージ オブジェクトの管理の特殊な難易度を解決する方法が 2 つあります。 クラス[CByteArray を](../../mfc/reference/cbytearray-class.md)使用するか、クラス[を使用](../../mfc/reference/clongbinary-class.md)することができます。 一般に`CByteArray`、大きなバイナリ データを管理する方法として推奨されます。

`CByteArray`より多くのオーバーヘッド`CLongBinary`を必要としますが[、CByteArray クラス](#_core_the_cbytearray_class)で説明されているように、より有能です。 `CLongBinary`[は、CLongBinary クラス](#_core_the_clongbinary_class)で簡単に説明されています。

大きなデータ項目`CByteArray`の使用の詳細については、テクニカル ノート[45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md)を参照してください。

## <a name="cbytearray-class"></a><a name="_core_the_cbytearray_class"></a>クラス

`CByteArray`は MFC コレクション クラスの 1 つです。 オブジェクト`CByteArray`はバイトの動的配列を格納します— 必要に応じて配列が拡張できます。 このクラスは、組み込みの C++ 配列と同様に、インデックスによる高速アクセスを提供します。 `CByteArray`オブジェクトは、診断のためにシリアル化およびダンプできます。 クラスは、指定されたバイトの取得と設定、バイトの挿入と追加、および 1 バイトまたはすべてのバイトの削除を行うメンバー関数を提供します。 これらの機能により、バイナリ データの解析が簡単になります。 たとえば、バイナリ オブジェクトが OLE オブジェクトの場合、実際のオブジェクトに到達するために、いくつかのヘッダー バイトを処理する必要があります。

## <a name="using-cbytearray-in-recordsets"></a><a name="_core_using_cbytearray_in_recordsets"></a>レコードセットでの CByteArray の使用

レコードセットのフィールド データ メンバに型`CByteArray`を与えることにより[、RFX](../../data/odbc/record-field-exchange-rfx.md)がレコードセットとデータ ソースとの間でこのようなオブジェクトの転送を管理し、オブジェクト内のデータを操作するための固定ベースを提供します。 RFX では、取得したデータに対して特定のサイトが必要であり、基になるデータにアクセスする方法が必要です。

大きなデータ項目`CByteArray`の使用の詳細については、テクニカル ノート[45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md)を参照してください。

## <a name="clongbinary-class"></a><a name="_core_the_clongbinary_class"></a>クラスを長くする

[CLongBinary](../../mfc/reference/clongbinary-class.md)オブジェクトは、ヒープに割り`HGLOBAL`当てられたストレージのブロックへのハンドルを囲む単純なシェルです。 バイナリ ラージ オブジェクトを含むテーブル列をバインドすると、RFX`HGLOBAL`はデータをレコードセットに転送する必要がある場合にハンドルを割り当`CLongBinary`て、レコードセットのフィールドにハンドルを格納します。

次に、`HGLOBAL`ハンドルを使用して、`m_hData`データ自体を操作し、ハンドル データと同様に操作します。 これは[、CByteArray](../../mfc/reference/cbytearray-class.md)が機能を追加する場所です。

> [!CAUTION]
> CLongBinary オブジェクトは、関数呼び出しのパラメーターとして使用できません。 さらに、その実装は、 を`::SQLGetData`呼び出すが、スクロール可能なスナップショットのスクロールのパフォーマンスを必ずしも遅くします。 これは、呼び出しを使用して`::SQLGetData`動的スキーマ列を取得する場合にも当てはまる場合があります。

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: 集計値の計算 (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)<br/>
[レコード フィールド エクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)
