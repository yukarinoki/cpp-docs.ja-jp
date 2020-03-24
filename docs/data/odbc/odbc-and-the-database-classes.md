---
title: ODBC とデータベース クラス
ms.date: 11/04/2016
helpviewer_keywords:
- database classes [C++], ODBC
- ODBC API functions [C++]
- ODBC classes [C++], MFC database classes
- MFC [C++], ODBC and
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
ms.openlocfilehash: 7c69f49cbe233eb0782fdaa9767ea55f4d04203c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213187"
---
# <a name="odbc-and-the-database-classes"></a>ODBC とデータベース クラス

MFC ODBC データベースクラスは、通常、 [CDatabase](../../mfc/reference/cdatabase-class.md)クラスおよび[CRecordset](../../mfc/reference/crecordset-class.md)クラスのメンバー関数に対して実行する odbc API 関数呼び出しをカプセル化します。 たとえば、複雑な ODBC 呼び出しシーケンス、返されたレコードのストレージの場所へのバインド、エラー条件の処理、およびその他の操作は、データベースクラスによって管理されます。 そのため、非常に単純なクラスインターフェイスを使用して、レコードセットオブジェクトを介してレコードを操作します。

> [!NOTE]
>  ODBC データ ソースには、ここで説明するように、MFC ODBC クラス経由でアクセスできます。また、MFC DAO (Data Access Object) クラス経由でもアクセスできます。

データベースクラスは、ODBC 機能をカプセル化しますが、ODBC API 関数の一対一のマッピングを提供しません。 データベースクラスは、Microsoft Access および Microsoft Visual Basic に含まれるデータアクセスオブジェクトの後にモデル化された、より高いレベルの抽象化を提供します。 詳細については、「 [ODBC および MFC](../../data/odbc/odbc-and-mfc.md)」を参照してください。

## <a name="see-also"></a>参照

[ODBC の基礎](../../data/odbc/odbc-basics.md)
