---
title: 'コンテナー: 複合ファイル |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 956a53587feb63706b824c502b46b09698f991be
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433037"
---
# <a name="containers-compound-files"></a>コンテナー : 複合ファイル

この記事では、コンポーネントと複合ファイルと利点の実装と、OLE アプリケーションで複合ファイルを使用する短所について説明します。

複合ファイルは、OLE の不可欠な部分です。 データ転送と OLE ドキュメント ストレージを容易にするために使用されます。 複合ファイルは、アクティブな構造化ストレージ モデルの実装です。 一貫性のあるインターフェイスには、ストレージ、ストリーム、またはファイル オブジェクトをシリアル化をサポートするが存在します。 複合ファイルが、クラスによって、Microsoft Foundation Class ライブラリでサポートされている`COleStreamFile`と`COleDocument`します。

> [!NOTE]
>  複合ファイルを使用しても、情報が OLE ドキュメントまたは複合ドキュメントから取得されるとは限りません。 複合ファイルは、複合ドキュメント、OLE ドキュメント、およびその他のデータを格納する方法の 1 つにすぎません。

##  <a name="_core_components_of_a_compound_file"></a> 複合ファイルのコンポーネント

OLE 複合ファイルで実装される 3 種類のオブジェクトを使用して: ストリーム オブジェクト、ストレージ オブジェクト、および`ILockBytes`オブジェクト。 これらのオブジェクトは、次の方法で、標準のファイル システムのコンポーネントに似ています。

- ファイルのように、Stream オブジェクトは、任意の型のデータを格納します。

- ディレクトリのように、ストレージ オブジェクトは、その他のストレージおよびストリーム オブジェクトを含めることができます。

- `LockBytes` オブジェクトは、ストレージ オブジェクトと、物理ハードウェア間のインターフェイスを表します。 記憶装置に実際のバイトを書き込む方法を判断する、`LockBytes`ハード ドライブなどのグローバル メモリの領域にオブジェクトがアクセスします。 詳細については`LockBytes`オブジェクトと`ILockBytes`インターフェイスを参照してください、 *OLE プログラマーズ リファレンス*します。

##  <a name="_core_advantages_and_disadvantages_of_compound_files"></a> 複合ファイルの長所と短所

複合ファイルは、file storage の従来の手法と利点を提供します。 Windows コモン コントロールには以下が含まれます。

- 増分のファイルにアクセスします。

- ファイル アクセス モード。

- ファイルの構造を標準化します。

複合ファイルの潜在的な欠点、フロッピー ディスク上の記憶域に関連する大きなのサイズとパフォーマンスの問題する必要がある対象となる場合を決定する、アプリケーションで使用するかどうか。

###  <a name="_core_incremental_access_to_files"></a> ファイルへのアクセスを増分

ファイルへの増分では、複合ファイルを使用する自動の特典です。 「内のファイル システム、ファイル」として複合ファイルを表示できるため、ストリームやストレージなどの個々 のオブジェクトの種類がファイル全体をロードすることがなくアクセスできます。 これは、ユーザーが編集するための新しいオブジェクトにアクセスする必要がある時間を短縮することができますが大幅にします。 増分更新では、オファーと同様のメリット、同じ概念に基づいています。 ファイル全体を 1 つのオブジェクトに加えられた変更を保存するだけではなく、OLE には、ユーザーによって編集される、ストリームまたは記憶域オブジェクトのみが保存されます。

###  <a name="_core_file_access_modes"></a> ファイル アクセス モード

複合ファイルを使用するもう 1 つのメリットは、複合ファイル内のオブジェクトに変更がディスクにコミットされたときに確認することです。 変更がコミットされるときにトランザクションまたはダイレクトでは、いずれかにファイルがアクセスは、モードを決定します。

- トランザクション モードでは、ユーザーが保存するか、変更を元に戻すまでで、古いと使用可能なドキュメントの新しいコピーの両方が確保されるため、複合ファイル内のオブジェクトを変更するのに 2 フェーズ コミット操作を使用します。

- 直接モードには、後でそれらを元に戻すことはできません、実行時のドキュメントへの変更が組み込まれています。

アクセス モードの詳細については、次を参照してください。、 *OLE プログラマーズ リファレンス*します。

###  <a name="_core_standardization"></a> 標準化

複合ファイルの構造を標準化には、実際には、ファイルを作成したアプリケーションの知識がないと OLE アプリケーションによって作成された複合ファイルを参照する別の OLE アプリケーションができます。

###  <a name="_core_size_and_performance_considerations"></a> サイズとパフォーマンスに関する考慮事項

他のファイルよりも大きくなる傾向がありますファイルがこの形式を使用して複合ファイル記憶域の構造とデータを段階的に保存する機能、複雑なので非構造化データを使用して、または記憶域を「フラット ファイル」です。 アプリケーションの頻繁に読み込みおよびファイルを保存する場合、は、複合ファイルを使用すると、ファイル サイズを増やす普通のファイルよりもはるかにすばやくを生成できます。 大規模な複合ファイルを取得することができます、ために保存され、フロッピー ディスクから読み込まれたファイルのアクセス時間も影響、その結果、低速のアクセスでファイル。

パフォーマンスに影響するもう 1 つの問題では、複合ファイルの断片化です。 複合ファイルのサイズ、ファイルで使用される最初と最後のディスク セクターの違い 断片化されたファイルは、データは含まれませんが、サイズを計算するときにカウントを空き領域の多くの領域を含めることができます。 複合ファイルの有効期間中は、これらの領域は、挿入、または記憶域オブジェクトの削除によって作成されます。

##  <a name="_core_using_compound_files_format_for_your_data"></a> 複合ファイルの形式を使用して、データ

派生したドキュメント クラスには、アプリケーションを正常に作成した後`COleDocument`のメイン ドキュメントのコンス トラクターを呼び出すことを確認`EnableCompoundFile`します。 アプリケーション ウィザードでは、OLE コンテナー アプリケーションを作成したときにこの呼び出しが挿入されます。

*OLE プログラマーズ リファレンス*を参照してください[IStream](/windows/desktop/api/objidl/nn-objidl-istream)、 [IStorage](/windows/desktop/api/objidl/nn-objidl-istorage)、および[ILockBytes](/windows/desktop/api/objidl/nn-objidl-ilockbytes)します。

## <a name="see-also"></a>関連項目

[コンテナー](../mfc/containers.md)<br/>
[コンテナー: ユーザー インターフェイスの問題](../mfc/containers-user-interface-issues.md)<br/>
[COleStreamFile クラス](../mfc/reference/colestreamfile-class.md)<br/>
[COleDocument クラス](../mfc/reference/coledocument-class.md)
