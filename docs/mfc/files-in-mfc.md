---
title: MFC のファイル
ms.date: 11/04/2016
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
ms.openlocfilehash: 3a99c4143bbd27ba765b0289b80be8870a940f63
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365310"
---
# <a name="files-in-mfc"></a>MFC のファイル

MFC クラス[CFile](../mfc/reference/cfile-class.md)クラスは、通常のファイル I/O 操作を処理します。 この記事ファミリでは、ファイルを開いたり閉じたり、それらのファイルに対してデータを読み書きする方法について説明します。 また、ファイルステータスの操作についても説明します。 MFC のオブジェクト ベースのシリアル化機能を、ファイル内のデータの読み取りと書き込みの代替手段として使用する方法については、「[シリアル化](../mfc/serialization-in-mfc.md)」を参照してください。

> [!NOTE]
> MFC`CDocument`オブジェクトを使用すると、フレームワークはシリアル化の多くを実行します。 特に、フレームワークはオブジェクトを`CFile`作成して使用します。 クラス`Serialize``CDocument`のメンバー関数のオーバーライドでコードを記述するだけで済みます。

この`CFile`クラスは、汎用のバイナリ ファイル操作用のインターフェイスを提供します。 から`CStdioFile`派生`CMemFile`したクラスと`CFile`派生`CMemFile`元`CSharedFile`のクラスは、より専門的なファイル サービスを提供します。

MFC ファイル処理の代替方法の詳細については、『ランタイム ライブラリ リファレンス』の[「ファイル処理](../c-runtime-library/file-handling.md)」を*参照してください*。

派生`CFile`クラスの詳細については[、MFC 階層グラフ](../mfc/hierarchy-chart.md)を参照してください。

## <a name="what-do-you-want-to-do"></a>どうしたいんですか

*Cファイルを使用する*

- [CFile でファイルを開く](../mfc/opening-files.md)

- [CFile を使用してファイルを読み書きする](../mfc/reading-and-writing-files.md)

- [CFile を使用してファイルを閉じる](../mfc/closing-files.md)

- [CFile を使用してファイルのステータスにアクセスする](../mfc/accessing-file-status.md)

*MFC シリアル化 (オブジェクトの永続性) を使用する*

- [シリアル化可能なクラスを作成する](../mfc/serialization-making-a-serializable-class.md)

- [CArchive オブジェクトを使用してオブジェクトをシリアル化する](../mfc/serialization-serializing-an-object.md)

- [CArchive オブジェクトを作成する](../mfc/two-ways-to-create-a-carchive-object.md)

- [CArchive <\<と >> 演算子を使用する](../mfc/using-the-carchive-output-and-input-operators.md)

- [アーカイブを使用して CObject および CObject 派生オブジェクトを保存およびロードする](../mfc/storing-and-loading-cobjects-via-an-archive.md)

## <a name="see-also"></a>関連項目

[概念](../mfc/mfc-concepts.md)<br/>
[MFC の一般的なトピック](../mfc/general-mfc-topics.md)<br/>
[CArchive クラス](../mfc/reference/carchive-class.md)<br/>
[Cオブジェクトクラス](../mfc/reference/cobject-class.md)
