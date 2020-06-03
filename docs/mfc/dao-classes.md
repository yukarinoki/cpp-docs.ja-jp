---
title: DAO クラス
ms.date: 09/17/2019
helpviewer_keywords:
- database classes [MFC], DAO
- DAO [MFC], classes
ms.assetid: b15d0cd6-328b-4288-9c19-d037a795db57
ms.openlocfilehash: 7ae85cbeb7790cadb8c26dfbdb7a5163dbcd47c0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373512"
---
# <a name="dao-classes"></a>DAO クラス

DAO は Access データベースで使用され、Office 2013 を通じてサポートされます。 DAO 3.6 は最終バージョンであり、廃止と見なされます。

これらのクラスは、他のアプリケーション フレームワーク クラスと連携して、Visual Basic と Access と同じデータベース エンジンを使用するデータ アクセス オブジェクト (DAO) データベースに簡単にアクセスできます。 DAO クラスは、オープン データベース接続 (ODBC) ドライバが利用可能なさまざまなデータベースにもアクセスできます。

DAO データベースを使用するプログラムには、少`CDaoDatabase`なくとも 1`CDaoRecordset`つのオブジェクトとオブジェクトが含まれます。

> [!NOTE]
> Visual C++ 環境およびウィザードでは DAO がサポートされなくなりました (ただし、DAO クラスは含まれていますが、使用することもできます)。 マイクロソフトでは、新しい MFC プロジェクトに ODBC を使用することをお勧めします。 DAO は、既存のアプリケーションの保守にのみ使用してください。

[CDaoWorkspace](../mfc/reference/cdaoworkspace-class.md)<br/>
名前付きのパスワードで保護されたデータベース セッションを、ログインからログオフまで管理します。 ほとんどのプログラムでは、既定のワークスペースが使用されます。

[CDaoDatabase](../mfc/reference/cdaodatabase-class.md)<br/>
データを操作できるデータベースへの接続。

[Cdaorecordset](../mfc/reference/cdaorecordset-class.md)<br/>
データ ソースから選択された 1 組のレコードセットを表現します。

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
コントロール内にデータベース レコードを表示するビューです。

[CDaoQueryDef](../mfc/reference/cdaoquerydef-class.md)<br/>
クエリ定義を表します。

[CDaoTableDef](../mfc/reference/cdaotabledef-class.md)<br/>
ベース テーブル、またはアタッチ テーブルの格納された定義を表現します。

[CDaoException](../mfc/reference/cdaoexception-class.md)<br/>
DAO クラスから発生する例外条件を表します。

[CDaoFieldExchange](../mfc/reference/cdaofieldexchange-class.md)<br/>
DAO データベース クラスで使われる DAO レコード フィールド エクスチェンジ (DFX: DAO Record Field eXchange) ルーチンをサポートします。 通常、このクラスは直接使用しません。

## <a name="related-classes"></a>関連するクラス

[CLongBinary](../mfc/reference/clongbinary-class.md)<br/>
ビットマップなどのバイナリ ラージ オブジェクト (BLOB) のストレージへのハンドルをカプセル化します。 `CLongBinary`オブジェクトは、データベーステーブルに格納されている大きなデータオブジェクトを管理するために使用されます。

[COleCurrency](../mfc/reference/colecurrency-class.md)<br/>
OLE オートメーション型**CURRENCY**のラッパーは、小数点より前に 15 桁、その後 4 桁の固定小数点演算型です。

[Coledatetime](../atl-mfc-shared/reference/coledatetime-class.md)<br/>
OLE オートメーションの**ラッパーは**DATE 型です。 日付と時刻の値を表します。

[COleVariant](../mfc/reference/colevariant-class.md)<br/>
OLE オートメーション型**VARIANT**のラッパー 。 **バリアント型**のデータは、さまざまな形式で格納できます。

## <a name="see-also"></a>関連項目

[クラスの概要](../mfc/class-library-overview.md)
