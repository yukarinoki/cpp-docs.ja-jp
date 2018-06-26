---
title: ファイルの読み書き |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CFile class [MFC], objects
- examples [MFC], reading files
- files [MFC], writing to
- examples [MFC], writing to files
- files [MFC], reading
- MFC, file operations
- CFile class [MFC], reading and writing CFile objects
- reading files
- writing to files [MFC]
ms.assetid: cac0c826-ba56-495f-99b3-ce6336f65763
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e30ee5b326833b45365c422238ecfcd4f82c556d
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930912"
---
# <a name="reading-and-writing-files"></a>ファイルの読み書き
C ランタイム ライブラリのファイル処理関数を使用している場合は、MFC の読み取りと書き込み操作が使い慣れた表示されます。 この説明から直接読み取りや書き込みに直接、`CFile`オブジェクト。 ことができますもはバッファー内のファイル I/O を[CArchive](../mfc/reference/carchive-class.md)クラスです。  
  
#### <a name="to-read-from-and-write-to-the-file"></a>読み取りと書き込み、ファイルに  
  
1.  使用して、`Read`と`Write`ファイルにデータを読み書きするメンバー関数。  
  
     - または -  
  
2.  `Seek`メンバー関数もファイル内の特定のオフセットに移動するために使用します。  
  
 `Read` バッファーに読み取るバイト数へのポインターを受け取りを実際に読み取られたバイト数を返します。 必要なバイト数読み取れなかったためファイルの終端 (EOF) に達すると、実際に読み取ったバイト数が返されます。 読み取りエラーが発生した場合は、例外がスローされます。 `Write` ような`Read`が書き込まれたバイト数が返されません。 指定すると、すべてのバイトを書き込んでいませんを含む、書き込みエラーが発生した場合、例外がスローされます。 有効ながある場合`CFile`オブジェクトからの読み取りまたは書き込みを次の例に示すようにできます。  
  
 [!code-cpp[NVC_MFCFiles#2](../atl-mfc-shared/reference/codesnippet/cpp/reading-and-writing-files_1.cpp)]  
  
> [!NOTE]
>  入力/出力操作内で通常実行する必要があります、**再試行**/**キャッチ**例外処理ブロック。 詳細については、次を参照してください。[例外処理 (MFC)](../mfc/exception-handling-in-mfc.md)です。  
  
## <a name="see-also"></a>関連項目  
 [ファイル](../mfc/files-in-mfc.md)

