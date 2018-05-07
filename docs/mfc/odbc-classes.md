---
title: ODBC クラス |Microsoft ドキュメント
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
- database classes [MFC], ODBC
- ODBC classes [MFC]
ms.assetid: 6c40fca8-3033-4873-9abe-7f51725de0e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98ef4509e7e7570d8c07013f0287fe01105e154a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="odbc-classes"></a>ODBC クラス
これらのクラスは作業をオープン データベース コネクティビティ (ODBC) ドライバーが利用可能なデータベースのさまざまなに簡単にアクセスを提供するその他のアプリケーション フレームワークのクラスを使用します。  
  
 ODBC データベースを使用するプログラムがありますが、少なくとも`CDatabase`オブジェクトおよび`CRecordset`オブジェクト。  
  
 [CDatabase](../mfc/reference/cdatabase-class.md)  
 それを通じてデータ ソースを操作することができます、データ ソースへの接続をカプセル化します。  
  
 [CRecordset](../mfc/reference/crecordset-class.md)  
 データ ソースから選択されたレコードのセットをカプセル化します。 レコード セットを有効にするレコード間をスクロール、(追加、編集、およびレコードの削除) のレコードを更新、フィルターで選択範囲を修飾する、選択範囲の並べ替えと取得した情報で選択をパラメーター化または実行時に計算します。  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 フォーム ビューのレコード セット オブジェクトに直接接続します。 ダイアログ データ エクス チェンジ レコード セットと、レコード ビューのコントロールの間 (DDX) メカニズム交換データ。 すべてのフォーム ビューと同様に、レコード ビューは、ダイアログ テンプレート リソースに基づいています。 レコード ビューは、レコード セットのレコード間を移動、レコードを更新し、レコード ビューを閉じるときに、関連するレコード セットを閉じるにもサポートされます。  
  
 [CDBException](../mfc/reference/cdbexception-class.md)  
 データ アクセス障害からの結果を処理する例外。 このクラスでは、クラス ライブラリの例外処理機構の他の例外クラスと同じ目的が機能します。  
  
 [CFieldExchange](../mfc/reference/cfieldexchange-class.md)  
 レコード フィールド エクス チェンジ (RFX)、フィールド データ メンバーと、レコード セット オブジェクトとデータ ソースに対応するテーブル列のデータ メンバーのパラメーター間のデータ交換をサポートするためにコンテキスト情報を提供します。 クラスに類似[CDataExchange](../mfc/reference/cdataexchange-class.md)、同様にダイアログ データ エクス (チェンジ DDX) に使用されます。  
  
## <a name="related-classes"></a>関連するクラス  
 [CLongBinary](../mfc/reference/clongbinary-class.md)  
 ビットマップなど、バイナリ ラージ オブジェクト (BLOB) の記憶域へのハンドルをカプセル化します。 `CLongBinary` オブジェクトを使用して、データベース テーブルに格納されている大規模なデータ オブジェクトを管理できます。  
  
 [CDBVariant](../mfc/reference/cdbvariant-class.md)  
 値のデータ型について心配する値を格納できます。 `CDBVariant` 共用体に格納されている現在の値のデータ型を追跡します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../mfc/class-library-overview.md)

