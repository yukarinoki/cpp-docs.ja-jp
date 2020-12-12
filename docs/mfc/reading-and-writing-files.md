---
description: 詳細については、「ファイルの読み取りと書き込み」を参照してください。
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
ms.openlocfilehash: 169135f57eaecb52605eca88b7f19e333551f1ad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248620"
---
# <a name="reading-and-writing-files"></a>ファイルの読み書き

C ランタイムライブラリのファイル処理関数を使用した場合、MFC の読み取りと書き込みの操作はよく知られています。 この記事では、オブジェクトに直接読み書きする方法について説明し `CFile` ます。 また、 [CArchive](../mfc/reference/carchive-class.md) クラスを使用してバッファーされたファイル i/o を実行することもできます。

#### <a name="to-read-from-and-write-to-the-file"></a>ファイルの読み取りと書き込みを行うには

1. `Read` `Write` ファイル内のデータの読み取りと書き込みを行うには、メンバー関数とメンバー関数を使用します。

     または

1. この `Seek` メンバー関数は、ファイル内の特定のオフセットに移動するためにも使用できます。

`Read` バッファーへのポインターと読み取るバイト数を取得し、読み取られた実際のバイト数を返します。 ファイルの終わり (EOF) に到達したために必要なバイト数を読み取れなかった場合は、実際に読み取られたバイト数が返されます。 読み取りエラーが発生した場合は、例外がスローされます。 `Write` はに似てい `Read` ますが、書き込まれたバイト数は返されません。 指定されたすべてのバイトを書き込むのではなく、書き込みエラーが発生した場合は、例外がスローされます。 有効なオブジェクトがある場合 `CFile` は、次の例に示すように、オブジェクトから読み取るか、またはそれに書き込むことができます。

[!code-cpp[NVC_MFCFiles#2](../atl-mfc-shared/reference/codesnippet/cpp/reading-and-writing-files_1.cpp)]

> [!NOTE]
> 通常は、 **`try`** / 例外処理ブロック内で入力/出力操作を実行する必要があり **`catch`** ます。 詳細については、「 [例外処理 (MFC)](../mfc/exception-handling-in-mfc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[[ファイル]](../mfc/files-in-mfc.md)
