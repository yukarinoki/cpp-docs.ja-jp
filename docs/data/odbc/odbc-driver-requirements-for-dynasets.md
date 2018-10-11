---
title: ダイナセットを使う場合の ODBC ドライバーの要件 |Microsoft Docs
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
ms.openlocfilehash: f6c7a9282ce1516ae3410307b74a66ba34adbcea
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2018
ms.locfileid: "49082710"
---
# <a name="odbc-driver-requirements-for-dynasets"></a>ダイナセットを使う場合の ODBC ドライバーの必要条件

ダイナセットでは、MFC ODBC データベース クラスで、動的プロパティを持つレコード セットです。特定の方法でデータ ソースと同期されたままになります。 MFC ダイナセットを使う場合 (ただし、前方スクロール専用レコード セット) でレベル 2 API 準拠 ODBC ドライバーが必要です。 場合のドライバー、[データソース](../../data/odbc/data-source-odbc.md)レベル 1 の API に準拠している設定すると、引き続き使用できますが、更新可能なと読み取り専用のスナップショットと順方向専用のレコード セット ダイナセットは。 ただし、拡張のフェッチとキーセット ドリブン カーソルをサポートしている場合は、レベル 1 のドライバーはダイナセットを使う場合をサポートできます。  
  
ODBC の用語でダイナセットを使う場合とスナップショットと呼びますカーソル。 カーソルは、レコード セット内の位置を追跡するために使用されるメカニズムです。 ダイナセットを使う場合のドライバーの要件の詳細については、次を参照してください。[ダイナセット](../../data/odbc/dynaset.md)します。 カーソルの詳細については、次を参照してください。、[オープン データベース コネクティビティ (ODBC)](/previous-versions/windows/desktop/ms710252) MSDN ドキュメント内の SDK です。  
  
> [!NOTE]
>  更新可能なレコード セットの場合、ODBC ドライバーが位置指定の update ステートメントのいずれかをサポートする必要がありますまたは`::SQLSetPos`ODBC API 関数。 MFC を使用して、両方がサポートされている場合`::SQLSetPos`効率が向上します。 また、スナップショットの場合は、更新可能なスナップショット (静的カーソルと位置指定の update ステートメント) に必要なサポートを提供するカーソル ライブラリを使用できます。  
  
## <a name="see-also"></a>関連項目  

[ODBC の基礎](../../data/odbc/odbc-basics.md)