---
title: DAO クラス
ms.date: 11/04/2016
f1_keywords:
- vc.classes.data
helpviewer_keywords:
- database classes [MFC], DAO
- DAO [MFC], classes
ms.assetid: b15d0cd6-328b-4288-9c19-d037a795db57
ms.openlocfilehash: 238aab0a1948f16a85b8ea16719b75b49f5e69c8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57287493"
---
# <a name="dao-classes"></a>DAO クラス

これらのクラスのデータ アクセス オブジェクト (DAO) のデータベースは、同じデータベース エンジンを使用して Microsoft Visual Basic および Microsoft Access を簡単にアクセスを付与するその他のアプリケーション フレームワーク クラスを使用します。 DAO クラスは、さまざまなオープン データベース コネクティビティ (ODBC) ドライバーは使用可能なデータベースにもアクセスできます。

DAO データベースを使用するプログラムになりますが、少なくとも`CDaoDatabase`オブジェクトと`CDaoRecordset`オブジェクト。

> [!NOTE]
>  Visual C 環境とウィザード、(ただし、DAO クラスが含まれていますし、それらを使用することもできます)、DAO をもはやサポートしません。 Microsoft では、新しい MFC プロジェクトでは、ODBC を使用することをお勧めします。 DAO は、既存のアプリケーションを維持するためにのみ使用する必要があります。

[CDaoWorkspace](../mfc/reference/cdaoworkspace-class.md)<br/>
ログインからログオフするデータベースの名前付きのパスワードで保護されたセッションを管理します。 ほとんどのプログラムでは、既定のワークスペースを使用します。

[CDaoDatabase](../mfc/reference/cdaodatabase-class.md)<br/>
データベースへの接続、それを通じてデータを操作することができます。

[CDaoRecordset](../mfc/reference/cdaorecordset-class.md)<br/>
データ ソースから選択された 1 組のレコードセットを表現します。

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
コントロール内にデータベース レコードを表示するビューです。

[CDaoQueryDef](../mfc/reference/cdaoquerydef-class.md)<br/>
通常は 1 つのデータベースに保存されているクエリの定義を表します。

[CDaoTableDef](../mfc/reference/cdaotabledef-class.md)<br/>
ベース テーブル、またはアタッチ テーブルの格納された定義を表現します。

[CDaoException](../mfc/reference/cdaoexception-class.md)<br/>
DAO クラスから発生する例外状態を表します。

[CDaoFieldExchange](../mfc/reference/cdaofieldexchange-class.md)<br/>
DAO データベース クラスで使われる DAO レコード フィールド エクスチェンジ (DFX: DAO Record Field eXchange) ルーチンをサポートします。 通常はこのクラスを直接使用します。

## <a name="related-classes"></a>関連するクラス

[CLongBinary](../mfc/reference/clongbinary-class.md)<br/>
ビットマップなどのバイナリ ラージ オブジェクト (BLOB) ストレージを識別するハンドルをカプセル化します。 `CLongBinary` オブジェクトは、データベース テーブルに格納されている大規模なデータ オブジェクトの管理に使用されます。

[COleCurrency](../mfc/reference/colecurrency-class.md)<br/>
OLE オートメーションの型のラッパー**通貨**小数点の前に、15 桁、4 桁の数字の後に、固定小数点の数値型。

[COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)<br/>
OLE オートメーションの型のラッパー**日付**します。 日付と時刻の値を表します。

[COleVariant](../mfc/reference/colevariant-class.md)<br/>
OLE オートメーションの型のラッパー**バリアント**します。 内のデータ**バリアント**多くの形式で保存することができます。

## <a name="see-also"></a>関連項目

[クラスの概要](../mfc/class-library-overview.md)
