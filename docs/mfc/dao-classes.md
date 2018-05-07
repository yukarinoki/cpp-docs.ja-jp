---
title: DAO クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.data
dev_langs:
- C++
helpviewer_keywords:
- database classes [MFC], DAO
- DAO [MFC], classes
ms.assetid: b15d0cd6-328b-4288-9c19-d037a795db57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f43595ca5f688372a70999231ceebec5282cd3b6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="dao-classes"></a>DAO クラス
これらのクラスは、データ アクセス オブジェクト (DAO) のデータベースは、同じデータベース エンジンを使用して Microsoft Visual Basic および Microsoft Access に簡単にアクセスを提供するその他のアプリケーション フレームワーク クラスによって使用します。 DAO クラスは、さまざまなオープン データベース コネクティビティ (ODBC) ドライバーが利用可能なデータベースにもアクセスできます。  
  
 DAO データベースを使用するプログラムがありますが、少なくとも`CDaoDatabase`オブジェクトおよび`CDaoRecordset`オブジェクト。  
  
> [!NOTE]
>  Visual C 環境とウィザードはサポートしなくなりました DAO (ただし、DAO クラスが含まれると、引き続き使用することができます)。 Microsoft では、新しい MFC プロジェクトでは、ODBC を使用することをお勧めします。 DAO は、既存のアプリケーションを保守でのみ使用する必要があります。  
  
 [CDaoWorkspace](../mfc/reference/cdaoworkspace-class.md)  
 ログインからログオフする、名前付きのパスワードで保護されたデータベース セッションを管理します。 ほとんどのプログラムは、既定のワークスペースを使用します。  
  
 [CDaoDatabase](../mfc/reference/cdaodatabase-class.md)  
 データベースへの接続、それを通じてデータを操作することができます。  
  
 [CDaoRecordset](../mfc/reference/cdaorecordset-class.md)  
 データ ソースから選択された 1 組のレコードセットを表現します。  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 コントロール内にデータベース レコードを表示するビューです。  
  
 [CDaoQueryDef](../mfc/reference/cdaoquerydef-class.md)  
 通常は 1 台のデータベースに保存されたクエリの定義を表します。  
  
 [どちら](../mfc/reference/cdaotabledef-class.md)  
 ベース テーブル、またはアタッチ テーブルの格納された定義を表現します。  
  
 [CDaoException](../mfc/reference/cdaoexception-class.md)  
 DAO クラスから発生する例外条件を表します。  
  
 [CDaoFieldExchange](../mfc/reference/cdaofieldexchange-class.md)  
 DAO データベース クラスで使われる DAO レコード フィールド エクスチェンジ (DFX: DAO Record Field eXchange) ルーチンをサポートします。 通常はこのクラスを直接使用します。  
  
## <a name="related-classes"></a>関連するクラス  
 [CLongBinary](../mfc/reference/clongbinary-class.md)  
 ビットマップなど、バイナリ ラージ オブジェクト (BLOB) の記憶域へのハンドルをカプセル化します。 `CLongBinary` オブジェクトを使用して、データベース テーブルに格納されている大規模なデータ オブジェクトを管理できます。  
  
 [COleCurrency](../mfc/reference/colecurrency-class.md)  
 OLE オートメーション型用のラッパー**通貨**、固定小数点の数値型で 15 桁小数点の前に、と後に 4 桁の数字を使用します。  
  
 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)  
 OLE オートメーション型用のラッパー**日付**です。 日付と時刻の値を表します。  
  
 [COleVariant](../mfc/reference/colevariant-class.md)  
 OLE オートメーション型用のラッパー**バリアント**です。 内のデータ**バリアント**s は、さまざま形式で格納できます。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../mfc/class-library-overview.md)

