---
title: ファイルを開く
ms.date: 11/04/2016
helpviewer_keywords:
- Open member functions [MFC]
- CFile class [MFC], variable
- opening files, in MFC
- Open calls [MFC]
- Open method, CFile class [MFC]
- examples [MFC], opening files
- opening files, handling exceptions
- exception handling [MFC], when opening files
- files [MFC], opening
- file objects [MFC]
- MFC, file operations
- opening files [MFC]
- exception handling [MFC], opening files
ms.assetid: a991b8ec-b04a-4766-b47e-7485b5dd0b01
ms.openlocfilehash: 6119bf922b05c30a14d8421800e3931c4a038779
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375957"
---
# <a name="opening-files"></a>ファイルを開く

MFC では、ファイルを開く最も一般的な方法は、2 段階のプロセスです。

#### <a name="to-open-a-file"></a>ファイルを開くには

1. パスまたはアクセス許可フラグを指定せずにファイル オブジェクトを作成します。

   通常、スタック フレームで[CFile](../mfc/reference/cfile-class.md)変数を宣言してファイル オブジェクトを作成します。

1. パスとアクセス許可フラグを指定して、ファイル オブジェクトの[Open](../mfc/reference/cfile-class.md#open)メンバー関数を呼び出します。

   ファイル`Open`が正常に開かれた場合は 0 以外の値、指定されたファイルを開けない場合は 0 になります。 メンバー`Open`関数は、次のようにプロトタイプ化されます。

   `virtual BOOL Open( LPCTSTR lpszFileName, UINT nOpenFlags, CFileException* pError = NULL );`

   オープン フラグは、ファイルに対するアクセス許可 (読み取り専用など) を指定します。 可能なフラグ値は`CFile`クラス内の列挙定数として定義されるため、 のように " "`CFile::`で修飾されます`CFile::modeRead`。 ファイルを`CFile::modeCreate`作成する場合は、フラグを使用します。

次の例は、読み取り/書き込み権限を持つ新しいファイルを作成する方法を示しています (前のファイルを同じパスに置き換えます)。

[!code-cpp[NVC_MFCFiles#1](../atl-mfc-shared/reference/codesnippet/cpp/opening-files_1.cpp)]

> [!NOTE]
> この例では、ファイルを作成して開きます。 問題がある場合、次に`Open`示すように、呼`CFileException`び出しは最後のパラメータにオブジェクトを返すことができます。 TRACE マクロは、ファイル名と、失敗の理由を示すコードの両方を出力します。 より詳細なエラー`AfxThrowFileException`報告が必要な場合は、この関数を呼び出すことができます。

## <a name="see-also"></a>関連項目

[CFile クラス](../mfc/reference/cfile-class.md)<br/>
[ファイル::開く](../mfc/reference/cfile-class.md#open)<br/>
[[ファイル]](../mfc/files-in-mfc.md)
