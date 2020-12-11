---
description: 詳細については、「MFC でのファイル」を参照してください。
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
ms.openlocfilehash: 47fab5876efd7d06ec4364721a09b7ed09da9744
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155047"
---
# <a name="files-in-mfc"></a>MFC のファイル

Microsoft Foundation Class ライブラリ (MFC) では、クラス [CFile](reference/cfile-class.md) は通常のファイル i/o 操作を処理します。 この記事の記事では、ファイルを開いたり閉じたりする方法について説明し、これらのファイルに対するデータの読み取りと書き込みを行う方法について説明します。 また、ファイルの状態の操作についても説明します。 ファイル内のデータの読み取りと書き込みを行う別の方法として、MFC のオブジェクトベースのシリアル化機能を使用する方法の詳細については、「 [シリアル化](serialization-in-mfc.md)」を参照してください。

> [!NOTE]
> MFC オブジェクトを使用すると、フレームワークによって `CDocument` 多くのシリアル化が機能します。 特に、フレームワークによってオブジェクトが作成され、使用され `CFile` ます。 クラスのメンバー関数のオーバーライドでコードを記述するだけで済み `Serialize` `CDocument` ます。

クラスは、 `CFile` 汎用のバイナリファイル操作のためのインターフェイスを提供します。 から派生したクラスと、から派生したクラスは、 `CStdioFile` `CMemFile` `CFile` `CSharedFile` `CMemFile` より専門的なファイルサービスを提供します。

MFC ファイル処理の代替方法の詳細については、「*ランタイムライブラリリファレンス*」の「[ファイル処理](../c-runtime-library/file-handling.md)」を参照してください。

派生クラスの詳細については、 `CFile` 「 [MFC 階層図](hierarchy-chart.md)」を参照してください。

## <a name="what-do-you-want-to-do"></a>どうしたいんですか

*CFile を使用する*

- [CFile でファイルを開きます。](opening-files.md)

- [CFile を使用したファイルの読み取りと書き込み](reading-and-writing-files.md)

- [CFile でファイルを閉じます](closing-files.md)

- [CFile でファイルの状態にアクセスする](accessing-file-status.md)

*MFC シリアル化の使用 (オブジェクトの永続化)*

- [Serializable クラスを作成する](serialization-making-a-serializable-class.md)

- [CArchive オブジェクトを介してオブジェクトをシリアル化する](serialization-serializing-an-object.md)

- [CArchive オブジェクトを作成する](two-ways-to-create-a-carchive-object.md)

- [CArchive <> 演算子を使用する \< and >](using-the-carchive-output-and-input-operators.md)

- [アーカイブを使用して通じた cobject および CObject から派生したオブジェクトを格納して読み込む](storing-and-loading-cobjects-via-an-archive.md)

## <a name="see-also"></a>関連項目

[概念](mfc-concepts.md)<br/>
[MFC の一般的なトピック](general-mfc-topics.md)<br/>
[CArchive クラス](reference/carchive-class.md)<br/>
[CObject クラス](reference/cobject-class.md)
