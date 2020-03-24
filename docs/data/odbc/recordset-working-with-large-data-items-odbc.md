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
ms.openlocfilehash: b84365461ce6d45fccdf1922974feff5af93f99f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212759"
---
# <a name="recordset-working-with-large-data-items-odbc"></a>レコードセット: 大量のデータの処理 (ODBC)

このトピックは、MFC ODBC クラスと MFC DAO クラスの両方に適用されます。

> [!NOTE]
>  MFC DAO クラスを使用している場合は、 [CLongBinary](../../mfc/reference/clongbinary-class.md)クラスではなくクラス[CByteArray](../../mfc/reference/cbytearray-class.md)を使用して、大きなデータ項目を管理します。 バルク行フェッチで MFC ODBC クラスを使用している場合は、`CByteArray`ではなく `CLongBinary` を使用します。 バルク行フェッチの詳細については、「レコード[セット: バルクデータフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)」を参照してください。

たとえば、ビットマップ (従業員の写真、地図、製品の画像、OLE オブジェクトなど) などの大きなデータをデータベースで格納できるとします。 この種類のデータは、次の理由により、バイナリラージオブジェクト (または BLOB) と呼ばれることがよくあります。

- 各フィールドの値は大きいです。

- 数値およびその他の単純なデータ型とは異なり、予測可能なサイズはありません。

- データは、プログラムの観点からは formless いません。

このトピックでは、このようなオブジェクトを操作するためにデータベースクラスで提供されるサポートについて説明します。

##  <a name="managing-large-objects"></a><a name="_core_managing_large_objects"></a>ラージオブジェクトの管理

レコードセットには、バイナリラージオブジェクトを管理するための特殊な難しさを解決する2つの方法があります。 クラス[CByteArray](../../mfc/reference/cbytearray-class.md)を使用することも、 [CLongBinary](../../mfc/reference/clongbinary-class.md)クラスを使用することもできます。 一般に、大規模なバイナリデータを管理するには、`CByteArray` をお勧めします。

`CByteArray` には `CLongBinary` よりも多くのオーバーヘッドが必要ですが、 [CByteArray クラス](#_core_the_cbytearray_class)で説明されているように、より多くの機能を利用できます。 `CLongBinary` については[、CLongBinary クラス](#_core_the_clongbinary_class)で簡単に説明します。

`CByteArray` を使用して大きなデータ項目を操作する方法の詳細については、「[テクニカルノート 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md)」を参照してください。

##  <a name="cbytearray-class"></a><a name="_core_the_cbytearray_class"></a>CByteArray クラス

`CByteArray` は、MFC コレクションクラスの1つです。 `CByteArray` オブジェクトは、動的なバイト配列を格納します。配列は必要に応じて拡張できます。 クラスは、組み込みのC++配列のように、インデックスによる高速アクセスを提供します。 `CByteArray` オブジェクトは、診断用にシリアル化およびダンプできます。 クラスは、指定されたバイトの取得と設定、バイトの挿入と追加、および1バイトまたはすべてのバイトの削除を行うためのメンバー関数を提供します。 これらの機能により、バイナリデータの解析が容易になります。 たとえば、バイナリオブジェクトが OLE オブジェクトの場合は、実際のオブジェクトに移動するためにヘッダーバイトを処理することが必要になることがあります。

##  <a name="using-cbytearray-in-recordsets"></a><a name="_core_using_cbytearray_in_recordsets"></a>レコードセットでの CByteArray の使用

レコードセットのフィールドデータメンバーに型 `CByteArray`を指定することにより、 [RFX](../../data/odbc/record-field-exchange-rfx.md)がレコードセットとデータソースの間のオブジェクトの転送を管理し、オブジェクト内のデータを操作できるようにするための固定ベースを提供します。 RFX は、データを取得するために特定のサイトを必要とします。また、基になるデータにアクセスする方法が必要です。

`CByteArray` を使用して大きなデータ項目を操作する方法の詳細については、「[テクニカルノート 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md)」を参照してください。

##  <a name="clongbinary-class"></a><a name="_core_the_clongbinary_class"></a>CLongBinary クラス

[CLongBinary](../../mfc/reference/clongbinary-class.md)オブジェクトは、ヒープに割り当てられたストレージのブロックを `HGLOBAL` ハンドルを囲む単純なシェルです。 バイナリラージオブジェクトを含むテーブル列をバインドすると、RFX はデータをレコードセットに転送する必要があるときに `HGLOBAL` ハンドルを割り当て、そのハンドルをレコードセットの `CLongBinary` フィールドに格納します。

さらに、`HGLOBAL` ハンドル、`m_hData`を使用してデータ自体を操作し、処理データの場合と同様に操作します。 ここで[CByteArray](../../mfc/reference/cbytearray-class.md)が機能を追加します。

> [!CAUTION]
>  CLongBinary オブジェクトは、関数呼び出しでパラメーターとして使用することはできません。 さらに、`::SQLGetData`を呼び出す実装では、スクロール可能なスナップショットのスクロールパフォーマンスが必ず低下します。 これは、`::SQLGetData` を使用して動的スキーマ列を取得する場合にも当てはまります。

## <a name="see-also"></a>参照

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: 集計値の計算 (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)<br/>
[レコード フィールド エクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)
