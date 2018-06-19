---
title: 例外クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.exception
dev_langs:
- C++
helpviewer_keywords:
- exception classes [MFC]
- exception handling [MFC], exception classes
- MFC, exceptions
ms.assetid: 1a2caf12-b3e9-4189-86d2-bf7a595bf025
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ce4085d0f5f2dcc73d126d04b7560ef8360ffd9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344897"
---
# <a name="exception-classes"></a>例外クラス
クラス ライブラリには、クラスに基づく例外処理機構が用意されています`CException`です。 アプリケーション フレームワークでは、そのコードの例外独自のコードにも使用できます。 詳細については、記事を参照してください。[例外](../mfc/exception-handling-in-mfc.md)です。 独自の例外型を派生できます`CException`です。  
  
 MFC は、サポートの例外のすべての例外クラスと同様に、独自の例外の派生元となる例外クラスを提供します。  
  
 [CException](../mfc/reference/cexception-class.md)  
 例外の基底クラス。  
  
 [CArchiveException](../mfc/reference/carchiveexception-class.md)  
 アーカイブの例外。  
  
 [CDaoException](../mfc/reference/cdaoexception-class.md)  
 DAO データベース操作でのエラーによる例外。  
  
 [CDBException](../mfc/reference/cdbexception-class.md)  
 ODBC データベースの処理中のエラーによる例外。  
  
 [CFileException](../mfc/reference/cfileexception-class.md)  
 ファイル指向の例外。  
  
 [CMemoryException](../mfc/reference/cmemoryexception-class.md)  
 メモリ不足の例外。  
  
 [CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md)  
 サポートされていない機能の使用による例外。  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 OLE の処理中のエラーによる例外。 このクラスは、コンテナーとサーバーの両方で使用されます。  
  
 [COleDispatchException](../mfc/reference/coledispatchexception-class.md)  
 オートメーション中のエラーによる例外。 オートメーションの例外では、オートメーション サーバーによってスローされ、オートメーション クライアントによってキャッチされました。  
  
 [CResourceException](../mfc/reference/cresourceexception-class.md)  
 Windows リソースの読み込みに失敗に起因する例外。  
  
 [CUserException](../mfc/reference/cuserexception-class.md)  
 ユーザーによる操作を停止するために使用する例外。 通常、ユーザーに通知されました、問題の前に、この例外がスローされます。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../mfc/class-library-overview.md)

