---
title: ODBC とデータベース クラス
ms.date: 11/04/2016
helpviewer_keywords:
- database classes [C++], ODBC
- ODBC API functions [C++]
- ODBC classes [C++], MFC database classes
- MFC [C++], ODBC and
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
ms.openlocfilehash: 6511aab9bb048882fe9c3398dd17f769eb16220c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320064"
---
# <a name="odbc-and-the-database-classes"></a>ODBC とデータベース クラス

MFC ODBC データベース クラスは、通常[、CDatabase](../../mfc/reference/cdatabase-class.md)クラスと[CRecordset](../../mfc/reference/crecordset-class.md)クラスのメンバー関数で自分自身を作成する ODBC API 関数呼び出しをカプセル化します。 たとえば、複雑な ODBC 呼び出しシーケンス、返されたレコードのストレージ位置へのバインド、エラー条件の処理、およびその他の操作は、データベース クラスによって管理されます。 その結果、レコードセット オブジェクトを使用してレコードを操作する場合は、かなり単純なクラス インターフェイスを使用します。

> [!NOTE]
> ODBC データ ソースには、ここで説明するように、MFC ODBC クラス経由でアクセスできます。また、MFC DAO (Data Access Object) クラス経由でもアクセスできます。

データベース クラスは ODBC 機能をカプセル化しますが、ODBC API 関数の 1 対 1 のマッピングは提供しません。 データベース クラスは、Access および Visual Basic で見つかったデータ アクセス オブジェクトをモデル化した、より高度な抽象化レベルを提供します。 詳細については、「 [ODBC および MFC](../../data/odbc/odbc-and-mfc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ODBC の基本](../../data/odbc/odbc-basics.md)
