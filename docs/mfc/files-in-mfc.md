---
title: MFC のファイル |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- serialization [MFC], MFC files
- I/O [MFC], MFC classes
- files [MFC], MFC
- files [MFC], serialization
- binary access, binary file operations in MFC
- file I/O classes [MFC]
- I/O [MFC]
- persistence [MFC]
- MFC, file operations
- files [MFC], manipulating
- binary access [MFC]
ms.assetid: ae25e2c5-2859-4679-ab97-438824e93ce1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 64a8df138ef0d581bcc93bf836ee0935a634983d
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930504"
---
# <a name="files-in-mfc"></a>MFC のファイル
Microsoft Foundation Class ライブラリ (MFC) でクラス[CFile](../mfc/reference/cfile-class.md)通常のファイル I/O 操作を処理します。 この一連のトピックでは、開くファイルを閉じるだけでなくしそれらのファイルにデータを書き込む方法を説明します。 ファイルの状態の操作についても説明します。 データ読み取りおよび書き込みファイル内の別の方法としての MFC オブジェクト ベースのシリアル化機能を使用する方法については、記事を参照してください。[シリアル化](../mfc/serialization-in-mfc.md)です。  
  
> [!NOTE]
>  MFC を使用すると`CDocument`フレームワークは、シリアル化操作の多くのオブジェクトします。 具体的には、フレームワークを作成して、`CFile`オブジェクト。 のみのオーバーライドでコードを記述する必要がある、`Serialize`クラスのメンバー関数`CDocument`です。  
  
 `CFile`クラスのインターフェイスのバイナリ ファイルを汎用的な操作を提供します。 `CStdioFile`と`CMemFile`から派生したクラス`CFile`と`CSharedFile`から派生したクラス`CMemFile`より専門的なファイル サービスを提供します。  
  
 MFC のファイルの処理に代わる方法の詳細については、次を参照してください。[ファイル処理](../c-runtime-library/file-handling.md)で、*ランタイム ライブラリ リファレンス*です。  
  
 については、派生した`CFile`クラスを参照してください、 [MFC 階層図](../mfc/hierarchy-chart.md)です。  
  
## <a name="what-do-you-want-to-do"></a>どうしたいんですか  
 *CFile を使用します。*  
  
-   [CFile でファイルを開く](../mfc/opening-files.md)  
  
-   [読み書き可能なファイルの読み書き](../mfc/reading-and-writing-files.md)  
  
-   [CFile のファイルを閉じる](../mfc/closing-files.md)  
  
-   [アクセスのファイル状態の操作](../mfc/accessing-file-status.md)  
  
 *MFC のシリアル化 (オブジェクトの持続性) を使用します。*  
  
-   [シリアル化可能なクラスを作成します。](../mfc/serialization-making-a-serializable-class.md)  
  
-   [CArchive オブジェクトを使用してオブジェクトをシリアル化します。](../mfc/serialization-serializing-an-object.md)  
  
-   [CArchive オブジェクトを作成します。](../mfc/two-ways-to-create-a-carchive-object.md)  
  
-   [CArchive を使用して <\<と >> 演算子](../mfc/using-the-carchive-output-and-input-operators.md)  
  
-   [保存し、読み込み CObjects およびアーカイブを通じた CObject の派生オブジェクト](../mfc/storing-and-loading-cobjects-via-an-archive.md)  
  
## <a name="see-also"></a>関連項目  
 [概念](../mfc/mfc-concepts.md)   
 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)   
 [CArchive クラス](../mfc/reference/carchive-class.md)   
 [CObject クラス](../mfc/reference/cobject-class.md)
