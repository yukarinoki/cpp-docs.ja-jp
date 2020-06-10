---
title: 例外クラス
ms.date: 11/04/2016
f1_keywords:
- vc.classes.exception
helpviewer_keywords:
- exception classes [MFC]
- exception handling [MFC], exception classes
- MFC, exceptions
ms.assetid: 1a2caf12-b3e9-4189-86d2-bf7a595bf025
ms.openlocfilehash: 907b34b12ffdaa70c4377a1012a66662fbba12d0
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619518"
---
# <a name="exception-classes"></a>例外クラス

クラスライブラリは、クラスに基づく例外処理機構を提供し `CException` ます。 アプリケーションフレームワークは、コード内で例外を使用します。また、自分で使用することもできます。 詳細については、「[例外](exception-handling-in-mfc.md)」を参照してください。 から独自の例外の種類を派生させることができ `CException` ます。

MFC には、例外クラスが用意されています。このクラスは、独自の例外だけでなく、サポートするすべての例外の例外クラスを派生させることができます。

[CException](reference/cexception-class.md)<br/>
例外の基底クラス。

[CArchiveException](reference/carchiveexception-class.md)<br/>
アーカイブの例外。

[CDaoException](reference/cdaoexception-class.md)<br/>
DAO データベース操作の失敗に起因する例外。

[CDBException](reference/cdbexception-class.md)<br/>
ODBC データベースの処理でエラーが発生したため、例外が発生します。

[CFileException](reference/cfileexception-class.md)<br/>
ファイル指向の例外。

[CMemoryException](reference/cmemoryexception-class.md)<br/>
メモリ不足の例外です。

[CNotSupportedException](reference/cnotsupportedexception-class.md)<br/>
サポートされていない機能を使用した結果として生成される例外。

[COleException](reference/coleexception-class.md)<br/>
OLE 処理のエラーによって発生する例外。 このクラスは、コンテナーとサーバーの両方で使用されます。

[COleDispatchException](reference/coledispatchexception-class.md)<br/>
オートメーション中のエラーによって発生する例外。 オートメーションの例外はオートメーションサーバーによってスローされ、オートメーションクライアントによってキャッチされます。

[CResourceException](reference/cresourceexception-class.md)<br/>
Windows リソースの読み込みに失敗した場合の例外。

[CUserException](reference/cuserexception-class.md)<br/>
ユーザーが開始した操作を停止するために使用される例外。 通常、この例外がスローされる前に、ユーザーに問題が通知されています。

## <a name="see-also"></a>関連項目

[クラスの概要](class-library-overview.md)
