---
title: 入出力処理の推奨事項 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- I/O [MFC], about I/O
- file-based I/O options
- I/O [MFC]
- I/O [MFC], options
- I/O [MFC], file-based options
ms.assetid: d664b175-3b4a-40c3-b14b-39de6b12e419
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9ee88b7784abb6ca622e72a9dfb31efc39fa7816
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930941"
---
# <a name="recommendations-for-handling-inputoutput"></a>入出力処理の推奨事項
ファイル ベースの I/O を使用するかどうかは、次のデシジョン ツリーの質問に応答する方法によって異なります。  
  
 **ディスク ファイルに格納されて、アプリケーションのプライマリ データ**  
  
-   はい、プライマリ データは、ディスク ファイルには。  
  
     **アプリケーションでファイルを開く上のメモリにファイル全体を読み取るし、ファイル全体で書き戻しをディスクにファイルの保存**  
  
    -   [はい] : これは、既定で MFC のドキュメントです。 使用して`CDocument`シリアル化します。  
  
    -   いいえ。 これは通常のファイルの更新トランザクション ベースの場合です。 トランザクションごとのファイルを更新し、必要はありません`CDocument`シリアル化します。  
  
-   いいえ、プライマリ データは、ディスク ファイルに存在しません。  
  
     **データが、ODBC データ ソースに存在します。**  
  
    -   [はい]、ODBC データ ソースのデータに存在します。  
  
         MFC データベース サポートを使用します。 この場合は、標準的な MFC 実装が含まれています、`CDatabase`オブジェクト、記事に説明したように[MFC: ドキュメントとビューを用いたデータベース クラス](../data/mfc-using-database-classes-with-documents-and-views.md)です。 アプリケーションの読み取りし、補助ファイルを書き込む可能性がありますも、アプリケーションのウィザード オプションの「データベース ビューとファイルの両方をサポート」の目的は、します。 この例では、補助ファイルのシリアル化を使用します。  
  
    -   いいえ、ODBC データ ソースのデータが存在しません。  
  
         この場合の例: で、ODBC DBMS 以外; に存在するデータOLE や DDE など、他のいくつかのメカニズムを使用して、データが読み取られます。  
  
         このような場合、シリアル化を使用しないし、アプリケーションはありませんが開いているメニュー項目を保存します。 使用する場合がありますが、`CDocument`ホーム ベースとしてと同様に、MFC ODBC アプリケーションを使用して、ドキュメントを格納する`CRecordset`オブジェクト。 フレームワークの既定のファイルを開くまたは保存ドキュメントのシリアル化を使用しません。  
  
 サポートし、オープン、save、ファイル メニューのコマンドを付けては、フレームワークは、ドキュメントのシリアル化を提供します。 シリアル化の読み書きデータ クラスから派生したオブジェクトを含む`CObject`、無期限に記憶域、通常、ディスク ファイル。 シリアル化は簡単に使用し、ニーズの多くは機能が、多くのデータ アクセス アプリケーションで適切でない可能性があります。 データ アクセス アプリケーションは、通常のトランザクションごとにデータを更新します。 トランザクションではなく読み取りや書き込みデータ ファイル全体を一度にによって影響を受けたレコードを更新します。  
  
 シリアル化の概要については、次を参照してください。[シリアル化](../mfc/serialization-in-mfc.md)です。  
  
## <a name="see-also"></a>関連項目  
 [シリアル化: シリアル化とデータベースの入力/出力](../mfc/serialization-serialization-vs-database-input-output.md)
