---
title: DAO クラス
ms.date: 09/17/2019
helpviewer_keywords:
- database classes [MFC], DAO
- DAO [MFC], classes
ms.assetid: b15d0cd6-328b-4288-9c19-d037a795db57
ms.openlocfilehash: 51abd29ef4de5d70f4a5b2b6b14b53510e7876a1
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615926"
---
# <a name="dao-classes"></a>DAO クラス

DAO は Access データベースで使用され、Office 2013 でサポートされています。 DAO 3.6 は最終バージョンであり、互換性のために残されているものと見なされます。

これらのクラスは、他のアプリケーションフレームワーククラスと連携して、Microsoft Visual Basic および Microsoft Access と同じデータベースエンジンを使用するデータアクセスオブジェクト (DAO) データベースに簡単にアクセスできるようにします。 DAO クラスは、Open Database Connectivity (ODBC) ドライバーを使用できるさまざまなデータベースにアクセスすることもできます。

DAO データベースを使用するプログラムには、少なく `CDaoDatabase` ともオブジェクトとオブジェクトがあり `CDaoRecordset` ます。

> [!NOTE]
> Visual C++ 環境とウィザードでは、DAO はサポートされなくなりました (ただし、DAO クラスは含まれていますが、引き続き使用できます)。 Microsoft では、新しい MFC プロジェクトに ODBC を使用することをお勧めします。 既存のアプリケーションを維持するには、DAO のみを使用する必要があります。

[CDaoWorkspace](reference/cdaoworkspace-class.md)<br/>
ログインからログオフまでの、名前付きのパスワードで保護されたデータベースセッションを管理します。 ほとんどのプログラムは既定のワークスペースを使用します。

[CDaoDatabase](reference/cdaodatabase-class.md)<br/>
データを操作できるデータベースへの接続。

[CDaoRecordset](reference/cdaorecordset-class.md)<br/>
データ ソースから選択された 1 組のレコードセットを表現します。

[CDaoRecordView](reference/cdaorecordview-class.md)<br/>
コントロール内にデータベース レコードを表示するビューです。

[CDaoQueryDef](reference/cdaoquerydef-class.md)<br/>
クエリ定義を表します。通常はデータベースに保存されます。

[CDaoTableDef](reference/cdaotabledef-class.md)<br/>
ベース テーブル、またはアタッチ テーブルの格納された定義を表現します。

[CDaoException](reference/cdaoexception-class.md)<br/>
DAO クラスに起因する例外条件を表します。

[CDaoFieldExchange](reference/cdaofieldexchange-class.md)<br/>
DAO データベース クラスで使われる DAO レコード フィールド エクスチェンジ (DFX: DAO Record Field eXchange) ルーチンをサポートします。 通常、このクラスは直接使用しません。

## <a name="related-classes"></a>関連クラス

[CLongBinary](reference/clongbinary-class.md)<br/>
ビットマップなどのバイナリラージオブジェクト (BLOB) のストレージへのハンドルをカプセル化します。 `CLongBinary`オブジェクトは、データベーステーブルに格納されている大規模なデータオブジェクトを管理するために使用されます。

[COleCurrency](reference/colecurrency-class.md)<br/>
OLE オートメーション型**CURRENCY**のラッパー (固定小数点演算型)。小数点の前に15桁、の後に4桁の数値が含まれます。

[COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)<br/>
OLE オートメーション型の**日付**のラッパー。 日付と時刻の値を表します。

[COleVariant](reference/colevariant-class.md)<br/>
OLE オートメーション型**バリアント**のラッパー。 **バリアント型**のデータは、さまざまな形式で格納できます。

## <a name="see-also"></a>関連項目

[クラスの概要](class-library-overview.md)
