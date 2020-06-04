---
title: 'コンテナー : 複合ファイル'
ms.date: 11/04/2016
helpviewer_keywords:
- compound files [MFC]
- compound documents
- containers [MFC], compound files
- OLE documents [MFC], compound files
- performance [MFC], compound files
- files [MFC], compound
- standardized file structure compound files
- documents [MFC], compound
- documents [MFC], OLE
- OLE containers [MFC], compound files
- access modes for files [MFC]
ms.assetid: 8b83cb3e-76c8-4bbe-ba16-737092b36f49
ms.openlocfilehash: 98166a355fd267ecbec0a7f0cc1d18fd0b2e7cd0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81353588"
---
# <a name="containers-compound-files"></a>コンテナー : 複合ファイル

この資料では、複合ファイルのコンポーネントと実装、および OLE アプリケーションで複合ファイルを使用する場合の利点と欠点について説明します。

複合ファイルは OLE の不可欠な部分です。 これらは、データ転送と OLE ドキュメントの保存を容易にするために使用されます。 複合ファイルは、アクティブな構造化ストレージ モデルの実装です。 ストレージ、ストリーム、またはファイル オブジェクトへのシリアル化をサポートする一貫性のあるインターフェイスが存在します。 複合ファイルは、クラス`COleStreamFile`と`COleDocument`でサポートされています。

> [!NOTE]
> 複合ファイルを使用しても、OLE ドキュメントまたは複合ドキュメントから情報が取得されるわけではありません。 複合ファイルは、複合ドキュメント、OLE ドキュメント、およびその他のデータを格納する方法の 1 つにすぎません。

## <a name="components-of-a-compound-file"></a><a name="_core_components_of_a_compound_file"></a>複合ファイルのコンポーネント

複合ファイルの OLE 実装では、ストリーム オブジェクト、ストレージ オブジェクト、および`ILockBytes`オブジェクトの 3 つのオブジェクトの種類を使用します。 これらのオブジェクトは、次の方法で標準ファイルシステムのコンポーネントと似ています。

- ストリーム オブジェクトは、ファイルと同様に、任意の種類のデータを格納します。

- ストレージ オブジェクトは、ディレクトリと同様に、他のストレージ オブジェクトやストリーム オブジェクトを含むことができます。

- `LockBytes`オブジェクトは、ストレージ オブジェクトと物理ハードウェア間のインターフェイスを表します。 これらのファイルは、`LockBytes`実際のバイトが、オブジェクトがアクセスしているストレージ デバイス (ハード ドライブやグローバル メモリ領域など) にどのように書き込まれるかを決定します。 オブジェクトとインターフェイスの`LockBytes``ILockBytes`詳細については、 OLE プログラマ リファレンス を*参照してください*。

## <a name="advantages-and-disadvantages-of-compound-files"></a><a name="_core_advantages_and_disadvantages_of_compound_files"></a>複合ファイルの長所と短所

複合ファイルは、以前のファイルストレージ方法では利用できない利点を提供します。 具体的な内容を次に示します。

- インクリメンタル ファイル アクセス。

- ファイル アクセス モード。

- ファイル構造の標準化。

複合ファイルの潜在的な欠点 (大きなサイズと、フロッピー ディスク上の記憶域に関するパフォーマンスの問題) は、アプリケーションで使用するかどうかを決定する際に考慮する必要があります。

### <a name="incremental-access-to-files"></a><a name="_core_incremental_access_to_files"></a>ファイルへの増分アクセス

ファイルへの増分アクセスは、複合ファイルを使用する場合の自動メリットです。 複合ファイルは「ファイル内のファイルシステム」と見なすことができるため、ストリームやストレージなどの個々のオブジェクトタイプにアクセスでき、ファイル全体をロードする必要はありません。 これにより、アプリケーションがユーザーによる編集のために新しいオブジェクトにアクセスする時間が大幅に短縮されます。 同じ概念に基づく増分更新でも同様の利点があります。 OLE は、1 つのオブジェクトに加えられた変更を保存するためだけにファイル全体を保存するのではなく、ユーザーが編集したストリームまたはストレージ オブジェクトだけを保存します。

### <a name="file-access-modes"></a><a name="_core_file_access_modes"></a>ファイル アクセス モード

複合ファイル内のオブジェクトへの変更がいつディスクにコミットされているかを判別できることは、複合ファイルを使用する利点です。 ファイルにアクセスするモードは、トランザクション処理または直接で、いつ変更がコミットされるか決定します。

- トランザクション モードでは、2 フェーズ のコミット操作を使用して複合ファイル内のオブジェクトを変更するため、ユーザーが変更を保存または元に戻すまで、ドキュメントの古いコピーと新しいコピーの両方を使用できます。

- 直接モードでは、後で元に戻す機能を持たずに、ドキュメントの変更を行った時点で反映します。

アクセス モードの詳細については、「 OLE プログラマ リファレンス 」を*参照してください*。

### <a name="standardization"></a><a name="_core_standardization"></a>標準化

複合ファイルの標準化された構造では、実際にファイルを作成したアプリケーションを知らずに、さまざまな OLE アプリケーションが OLE アプリケーションによって作成された複合ファイルを参照できます。

### <a name="size-and-performance-considerations"></a><a name="_core_size_and_performance_considerations"></a>サイズとパフォーマンスに関する考慮事項

複合ファイルのストレージ構造が複雑になり、データを増分的に保存する機能が増えるため、この形式を使用するファイルは、非構造化または「フラット ファイル」ストレージを使用する他のファイルよりも大きくなる傾向があります。 アプリケーションで頻繁にファイルをロードおよび保存する場合、複合ファイルを使用すると、非複合ファイルよりもファイルサイズが大幅に増加する可能性があります。 複合ファイルは大きくなる可能性があるため、フロッピー ディスクに保存され、フロッピー ディスクから読み込まれるファイルのアクセス時間にも影響を受け、ファイルへのアクセスが遅くなる可能性があります。

パフォーマンスに影響するもう 1 つの問題は、複合ファイルの断片化です。 複合ファイルのサイズは、ファイルが使用する最初と最後のディスクセクタの差によって決まります。 断片化されたファイルには、データを含まないが、サイズを計算するときにカウントされる空き領域の領域を多数含めることができます。 複合ファイルの有効期間中、これらの領域は、ストレージ オブジェクトの挿入または削除によって作成されます。

## <a name="using-compound-files-format-for-your-data"></a><a name="_core_using_compound_files_format_for_your_data"></a>データに複合ファイル形式を使用する

から`COleDocument`派生したドキュメント クラスを持つアプリケーションが正常に作成された後、メイン ドキュメント`EnableCompoundFile`コンストラクターが を呼び出していることを確認します。 アプリケーション ウィザードで OLE コンテナー アプリケーションを作成すると、この呼び出しが自動的に挿入されます。

OLE*プログラマ リファレンス*の「 [IStream](/windows/win32/api/objidl/nn-objidl-istream)、 [IStorage](/windows/win32/api/objidl/nn-objidl-istorage)、および[ILockBytes](/windows/win32/api/objidl/nn-objidl-ilockbytes)」を参照してください。

## <a name="see-also"></a>関連項目

[Containers](../mfc/containers.md)<br/>
[コンテナー : ユーザー インターフェイスの問題](../mfc/containers-user-interface-issues.md)<br/>
[クラス](../mfc/reference/colestreamfile-class.md)<br/>
[COleDocument クラス](../mfc/reference/coledocument-class.md)
