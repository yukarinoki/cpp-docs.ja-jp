---
title: ファイルの読み書き
ms.date: 11/04/2016
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
ms.openlocfilehash: 6c4b2b21bbfa19fb73997f8475cfa9a4047dc0ca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371797"
---
# <a name="reading-and-writing-files"></a>ファイルの読み書き

C ランタイム ライブラリのファイル処理関数を使用している場合は、MFC の読み取りおよび書き込み操作が使い慣れたように見えます。 この記事では、オブジェクトから直接読み取り、`CFile`オブジェクトに直接書き込む方法について説明します。 [CArchive](../mfc/reference/carchive-class.md)クラスを使用してバッファ付きファイル I/O を実行することもできます。

#### <a name="to-read-from-and-write-to-the-file"></a>ファイルの読み取りと書き込みを行う

1. および`Write``Read`メンバー関数を使用して、ファイル内のデータの読み取りと書き込みを行います。

     \- または -

1. メンバー`Seek`関数は、ファイル内の特定のオフセットに移動することもできます。

`Read`は、バッファーへのポインタと読み取るバイト数を受け取り、読み取られた実際のバイト数を返します。 ファイルの終わり (EOF) に達したために必要なバイト数を読み取ることができなかった場合は、実際に読み取られたバイト数が返されます。 読み取りエラーが発生した場合は、例外がスローされます。 `Write`は に`Read`似ていますが、書き込まれたバイト数は返されません。 指定されたバイトの一方を書き込まないなど、書き込みエラーが発生すると、例外がスローされます。 有効な`CFile`オブジェクトがある場合は、次の例に示すように、オブジェクトから読み取るか、書き込むことができます。

[!code-cpp[NVC_MFCFiles#2](../atl-mfc-shared/reference/codesnippet/cpp/reading-and-writing-files_1.cpp)]

> [!NOTE]
> 通常は、**キャッチ**/**例外**処理ブロックの内部で入出力操作を実行する必要があります。 詳細については、「[例外処理 (MFC)](../mfc/exception-handling-in-mfc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[[ファイル]](../mfc/files-in-mfc.md)
