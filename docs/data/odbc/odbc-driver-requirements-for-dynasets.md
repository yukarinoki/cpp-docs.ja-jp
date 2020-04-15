---
title: ダイナセットを使う場合の ODBC ドライバーの必要条件
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets, dynasets
- drivers, for dynasets
- drivers, ODBC
- recordsets, dynasets
- dynasets
- ODBC drivers, dynasets
ms.assetid: 585cc67b-4d92-404b-9903-d769cd17badc
ms.openlocfilehash: c612e8ea91882a6e744a8f47afe0decbeba85358
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367215"
---
# <a name="odbc-driver-requirements-for-dynasets"></a>ダイナセットを使う場合の ODBC ドライバーの必要条件

MFC ODBC データベース クラスでは、ダイナセットは動的プロパティを持つレコードセットです。これらは、特定の方法でデータ ソースと同期されたままになります。 MFC ダイナセット (前方専用レコードセットではない) には、レベル 2 の API 準拠の ODBC ドライバが必要です。 [データ ソース](../../data/odbc/data-source-odbc.md)のドライバーがレベル 1 API セットに準拠している場合でも、更新可能なスナップショットと読み取り専用スナップショットと前方専用レコードセットの両方を使用できますが、ダイナセットは使用できません。 ただし、レベル 1 ドライバーは、拡張フェッチおよびキーセット ドリブン カーソルをサポートする場合は、ダイナセットをサポートできます。

ODBC 用語では、ダイナセットとスナップショットはカーソルと呼ばれます。 カーソルは、レコードセット内での位置を追跡するために使用されるメカニズムです。 ダイナセットのドライバ要件の詳細については、「[ダイナセット](../../data/odbc/dynaset.md)」を参照してください。 カーソルの詳細については、MSDN ドキュメントの[オープン データベース接続 (ODBC)](/sql/odbc/microsoft-open-database-connectivity-odbc) SDK を参照してください。

> [!NOTE]
> 更新可能なレコードセットの場合、ODBC ドライバーは位置指定更新ステートメントまたは`::SQLSetPos`ODBC API 関数をサポートする必要があります。 両方がサポートされている場合、MFC`::SQLSetPos`は効率を高めます。 または、スナップショットの場合は、更新可能なスナップショット (静的カーソルおよび位置指定更新ステートメント) に必要なサポートを提供するカーソル ライブラリを使用できます。

## <a name="see-also"></a>関連項目

[ODBC の基本](../../data/odbc/odbc-basics.md)
