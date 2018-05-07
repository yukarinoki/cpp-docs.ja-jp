---
title: ダイナセットを使う場合の ODBC ドライバーの必要条件 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets, dynasets
- drivers, for dynasets
- drivers, ODBC
- recordsets, dynasets
- dynasets
- ODBC drivers, dynasets
ms.assetid: 585cc67b-4d92-404b-9903-d769cd17badc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d9fad26440cea2c8ec2efd7d07dacb83547252e3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="odbc-driver-requirements-for-dynasets"></a>ダイナセットを使う場合の ODBC ドライバーの必要条件
ダイナセットでは、MFC ODBC データベース クラスで、動的なプロパティを持つレコード セットです。特定の方法でデータ ソースと同期されたままになります。 MFC ダイナセットを使う場合 (ただし、前方スクロール専用レコード セット) 準拠のレベル 2 の API の ODBC ドライバーが必要です。 場合のドライバー、[データソース](../../data/odbc/data-source-odbc.md)レベル 1 の API に準拠している設定すると、使用できますが、更新可能なと読み取り専用のスナップショットと順方向専用レコード セットでは、ダイナセットはします。 ただし、レベル 1 のドライバーは、拡張フェッチとキーセット ドリブン カーソルがサポートされている場合、ダイナセットをサポートできます。  
  
 ODBC 用語では、ダイナセットを使う場合とスナップショットと呼ばれるカーソル。 カーソルは、レコード セット内での位置を追跡するために使用されるメカニズムです。 ダイナセットを使う場合のドライバーの要件の詳細については、次を参照してください。[ダイナセット](../../data/odbc/dynaset.md)です。 カーソルの詳細については、次を参照してください。、[オープン データベース コネクティビティ (ODBC)](https://msdn.microsoft.com/en-us/library/ms710252.aspx) SDK MSDN ドキュメントにします。  
  
> [!NOTE]
>  更新可能なレコード セットの場合、ODBC ドライバーが位置指定の update ステートメントのいずれかをサポートする必要がありますまたは **:: SQLSetPos** ODBC API 関数。 MFC を使用して、両方がサポートされている場合 **:: SQLSetPos**効率を上げるのためです。 代わりに、スナップショット、更新可能なスナップショット (静的カーソルと位置指定の update ステートメント) に必要なサポートを提供する、カーソル ライブラリを使用できます。  
  
## <a name="see-also"></a>関連項目  
 [ODBC の基礎](../../data/odbc/odbc-basics.md)