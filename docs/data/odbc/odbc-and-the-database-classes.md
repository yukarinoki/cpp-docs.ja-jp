---
title: ODBC とデータベース クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- database classes [C++], ODBC
- ODBC API functions [C++]
- ODBC classes [C++], MFC database classes
- MFC [C++], ODBC and
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: abbb20b76f8e24a9b0f20961728dd8e428733654
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33088468"
---
# <a name="odbc-and-the-database-classes"></a>ODBC とデータベース クラス
MFC ODBC データベース クラスは、通常行う自分で、メンバー内の関数、ODBC API 関数呼び出しをカプセル化する、 [CDatabase](../../mfc/reference/cdatabase-class.md)と[CRecordset](../../mfc/reference/crecordset-class.md)クラスです。 たとえば、複雑な odbc 呼び出し、記憶域の場所、エラー状態の処理およびその他の操作に返されるレコードのバインドは管理するデータベース クラスでされます。 その結果、かなりシンプルなインターフェイスとクラスを使用して、レコード セット オブジェクトを使用してレコードを操作します。  
  
> [!NOTE]
>  ODBC データ ソースには、ここで説明するように、MFC ODBC クラス経由でアクセスできます。また、MFC DAO (Data Access Object) クラス経由でもアクセスできます。  
  
 データベース クラスには、ODBC の機能がカプセル化が ODBC API 関数の 1 対 1 のマッピングは提供しません。 データベース クラスより高度な抽象化、データ アクセス オブジェクトは、Microsoft Access や Microsoft Visual Basic で見つかったとしてモデル化を提供します。 詳細については、次を参照してください。 [ODBC と MFC](../../data/odbc/odbc-and-mfc.md)です。  
  
## <a name="see-also"></a>関連項目  
 [ODBC の基礎](../../data/odbc/odbc-basics.md)