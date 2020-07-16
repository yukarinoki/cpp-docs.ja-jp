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
ms.openlocfilehash: 4c436764649a1aa418e12300809482b45224dd46
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "86403843"
---
# <a name="odbc-driver-requirements-for-dynasets"></a>ダイナセットを使う場合の ODBC ドライバーの必要条件

MFC ODBC データベースクラスでは、ダイナセットは動的プロパティを持つレコードセットです。これらのファイルは、特定の方法でデータソースと同期されたままになります。 MFC のダイナセット (前方参照専用のレコードセットを除く) には、レベル2の API に準拠した ODBC ドライバーが必要です。 [データソース](../../data/odbc/data-source-odbc.md)のドライバーがレベル1の API セットに準拠している場合でも、更新可能なスナップショットと読み取り専用のスナップショットと順方向専用のレコードの両方を使用できますが、ダイナセットは使用できません。 ただし、拡張フェッチとキーセットドリブンカーソルがサポートされている場合は、レベル1のドライバーでダイナセットがサポートされることがあります。

ODBC の用語では、ダイナセットとスナップショットはカーソルと呼ばれます。 カーソルは、レコードセット内のその位置を追跡するために使用されるメカニズムです。 ダイナセットのドライバー要件の詳細については、「[ダイナセット](../../data/odbc/dynaset.md)」を参照してください。 カーソルの詳細については、 [Open Database Connectivity (ODBC)](/sql/odbc/microsoft-open-database-connectivity-odbc)のドキュメントを参照してください。

> [!NOTE]
> 更新可能なレコードセットの場合、ODBC ドライバーは、配置された update ステートメントまたは odbc API 関数のいずれかをサポートしている必要があり `::SQLSetPos` ます。 両方がサポートされている場合、MFC は `::SQLSetPos` 効率を向上させるためにを使用します。 また、スナップショットの場合は、更新可能なスナップショット (静的カーソルおよび位置指定更新ステートメント) に必要なサポートを提供するカーソルライブラリを使用できます。

## <a name="see-also"></a>関連項目

[ODBC の基礎](../../data/odbc/odbc-basics.md)
