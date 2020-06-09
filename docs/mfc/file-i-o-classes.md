---
title: ファイル i/o クラス
ms.date: 11/04/2016
f1_keywords:
- vc.classes.file
helpviewer_keywords:
- disk file classes [MFC]
- stdio classes [MFC]
- OLE streams [MFC]
- I/O [MFC], MFC classes
- translated stream classes [MFC]
- file I/O classes [MFC]
- I/O [MFC], classes
- sockets classes [MFC]
- stream classes [MFC]
- memory file classes [MFC]
ms.assetid: 92821c3f-d9e1-47f6-98c9-3b632d86e811
ms.openlocfilehash: 2fcf4dfc1388df0df2bc25928ec8541486c6bb2d
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615668"
---
# <a name="file-io-classes"></a>ファイル I/O クラス

これらのクラスは、従来のディスクファイル、メモリ内ファイル、アクティブなストリーム、および Windows ソケットに対するインターフェイスを提供します。 から派生したすべてのクラスを `CFile` オブジェクトと共に使用して、 `CArchive` シリアル化を実行できます。

`CArchive` `CFile` 独自の入出力処理を作成する場合は、特に、次のクラスを使用します。 通常、これらのクラスから派生する必要はありません。 アプリケーションフレームワークを使用する場合、ドキュメントの関数をオーバーライドしてドキュメントの内容を**File**シリアル化する方法の**Open** **Save** `CArchive` `Serialize` 詳細を指定する限り、[ファイル] メニューの [開く] および [保存] コマンドの既定の実装では、(クラスを使用して) ファイル i/o が処理されます。 ファイルクラスとシリアル化の詳細については、「 [MFC のファイル](files-in-mfc.md)と[シリアル化](serialization-in-mfc.md)」を参照してください。

[CFile](reference/cfile-class.md)<br/>
バイナリディスクファイルへのファイルインターフェイスを提供します。

[CStdioFile](reference/cstdiofile-class.md)<br/>
`CFile`通常はテキストモードでバッファリングされたストリームディスクファイルへのインターフェイスを提供します。

[CMemFile](reference/cmemfile-class.md)<br/>
`CFile`インメモリファイルへのインターフェイスを提供します。

[CSharedFile](reference/csharedfile-class.md)<br/>
`CFile`共有メモリ内ファイルへのインターフェイスを提供します。

[COleStreamFile](reference/colestreamfile-class.md)<br/>
は、COM インターフェイスを使用して、 `IStream` `CFile` 複合ファイルにアクセスできるようにします。

[CSocketFile](reference/csocketfile-class.md)<br/>
`CFile`Windows ソケットへのインターフェイスを提供します。

## <a name="related-classes"></a>関連クラス

[CArchive](reference/carchive-class.md)<br/>
Cooperates オブジェクトを使用して、 `CFile` シリアル化によってオブジェクトの永続的なストレージを実装します ( [CObject:: Serialize](reference/cobject-class.md#serialize)を参照)。

[CArchiveException](reference/carchiveexception-class.md)<br/>
アーカイブの例外。

[CFileException](reference/cfileexception-class.md)<br/>
ファイル指向の例外。

[CFileDialog](reference/cfiledialog-class.md)<br/>
ファイルを開く、または保存するための標準のダイアログボックスを提供します。

[CRecentFileList](reference/crecentfilelist-class.md)<br/>
最近使用した (MRU) ファイルの一覧を保持します。

## <a name="see-also"></a>関連項目

[クラスの概要](class-library-overview.md)
