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
ms.openlocfilehash: 3507a5ee7dcfb8bf4f4eee12ef9264c16ad904c2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213110"
---
# <a name="odbc-driver-requirements-for-dynasets"></a>ダイナセットを使う場合の ODBC ドライバーの必要条件

MFC ODBC データベースクラスでは、ダイナセットは動的プロパティを持つレコードセットです。これらのファイルは、特定の方法でデータソースと同期されたままになります。 MFC のダイナセット (前方参照専用のレコードセットを除く) には、レベル2の API に準拠した ODBC ドライバーが必要です。 [データソース](../../data/odbc/data-source-odbc.md)のドライバーがレベル1の API セットに準拠している場合でも、更新可能なスナップショットと読み取り専用のスナップショットと順方向専用のレコードの両方を使用できますが、ダイナセットは使用できません。 ただし、拡張フェッチとキーセットドリブンカーソルがサポートされている場合は、レベル1のドライバーでダイナセットがサポートされることがあります。

ODBC の用語では、ダイナセットとスナップショットはカーソルと呼ばれます。 カーソルは、レコードセット内のその位置を追跡するために使用されるメカニズムです。 ダイナセットのドライバー要件の詳細については、「[ダイナセット](../../data/odbc/dynaset.md)」を参照してください。 カーソルの詳細については、MSDN ドキュメントの[Open Database Connectivity (ODBC)](/sql/odbc/microsoft-open-database-connectivity-odbc) SDK を参照してください。

> [!NOTE]
>  更新可能なレコードセットの場合、ODBC ドライバーは、配置された update ステートメントまたは `::SQLSetPos` ODBC API 関数をサポートしている必要があります。 両方がサポートされている場合、MFC では効率を上げるために `::SQLSetPos` を使用します。 また、スナップショットの場合は、更新可能なスナップショット (静的カーソルおよび位置指定更新ステートメント) に必要なサポートを提供するカーソルライブラリを使用できます。

## <a name="see-also"></a>参照

[ODBC の基礎](../../data/odbc/odbc-basics.md)
