---
title: 'コンテナー: 複合ファイル |Microsoft ドキュメント'
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
ms.openlocfilehash: 8983fd8cb51a9f305ef4b0fad4d546fc8091f5a5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348346"
---
# <a name="containers-compound-files"></a>コンテナー : 複合ファイル
この記事では、コンポーネントと複合ファイルと利点の実装の長所と短所、OLE アプリケーションで複合ファイルについて説明します。  
  
 複合ファイルは、OLE の不可欠な部分です。 データ転送および OLE ドキュメントの格納を容易にするために使用されます。 複合ファイルは、アクティブな構造化ストレージ モデルの実装です。 一貫性のあるインターフェイスには、ストレージ、ストリーム、またはファイル オブジェクトをシリアル化をサポートするが存在します。 複合ファイルがクラスによって、Microsoft Foundation Class ライブラリでサポートされている`COleStreamFile`と`COleDocument`です。  
  
> [!NOTE]
>  複合ファイルを使用しても、OLE ドキュメントまたは複合ドキュメントから情報を取得するとは限りません。 複合ファイルは、複合ドキュメント、OLE ドキュメント、およびその他のデータを保存する方法の 1 つです。  
  
##  <a name="_core_components_of_a_compound_file"></a> 複合ファイルのコンポーネント  
 OLE 複合ファイルで実装される 3 種類のオブジェクトを使用して: ストリーム オブジェクト、ストレージ オブジェクト、および`ILockBytes`オブジェクト。 これらのオブジェクトは、次の方法で標準的なファイル システムのコンポーネントに似ています。  
  
-   ファイルの場合と同様に、ストリーム オブジェクトは、任意の型のデータを格納します。  
  
-   ディレクトリのように、ストレージ オブジェクトには、その他の記憶域とストリーム オブジェクトを含めることができます。  
  
-   **LockBytes**オブジェクトは、記憶域オブジェクトと、物理ハードウェア間のインターフェイスを表します。 実際のバイト数がどのような記憶域デバイスに書き込まれる方法を判断する、 **LockBytes**オブジェクトにアクセスする、ハード ドライブなどのグローバル メモリの領域。 詳細については**LockBytes**オブジェクトおよび`ILockBytes`インターフェイスを参照してください、 *OLE プログラマーズ リファレンス*です。  
  
##  <a name="_core_advantages_and_disadvantages_of_compound_files"></a> 複合ファイルの長所と短所  
 複合ファイルでは、ファイル ストレージの以前のメソッドで不可の利点があります。 Windows コモン コントロールには以下が含まれます。  
  
-   増分のファイルにアクセスします。  
  
-   ファイル アクセス モードです。  
  
-   ファイルの構造を標準化します。  
  
 複合ファイルの潜在的な欠点 — フロッピー ディスク上の記憶域に関連する大きなのサイズとパフォーマンスの問題-必要があるときに考慮されるを決定する、アプリケーションで使用するかどうか。  
  
###  <a name="_core_incremental_access_to_files"></a> 増分ファイルにアクセスします。  
 増分ファイルにアクセスするには、複合ファイルを使用する自動の利点です。 複合ファイルは、「内のファイル システム、ファイル」と見なすことができます、ために、全体のファイルを読み込む必要がないストリームやストレージなどの個々 のオブジェクトの種類をアクセスすることができます。 ユーザーによる編集のための新しいオブジェクトにアクセスする必要があるアプリケーション時間を大幅に短縮このことができます。 増分更新は、オファーのような利点があります、同じ概念に基づいています。 ファイル全体を 1 つのオブジェクトへの変更を保存するだけではなく、OLE には、ユーザーによって編集、ストリームまたは記憶域オブジェクトのみが保存されます。  
  
###  <a name="_core_file_access_modes"></a> ファイル アクセス モード  
 複合ファイル内のオブジェクトへの変更がディスクにコミットされた場合を判断できるとは、複合ファイルを使用する利点の 1 つです。 ファイルにアクセス、直接、または一括モードでは、変更がコミットされるときを判断します。  
  
-   トランザクション モードでは、ユーザーを保存するか、変更を取り消すまでで、新旧両方の使用可能なドキュメントの新しいコピーが確保されるため、複合ファイル内のオブジェクトを変更するのに、2 フェーズ コミット操作を使用します。  
  
-   ダイレクト モードには、それらを後で元に戻す機能がない場合に、ドキュメントへの変更が組み込まれています。  
  
 アクセス モードの詳細については、次を参照してください。、 *OLE プログラマーズ リファレンス*です。  
  
###  <a name="_core_standardization"></a> 標準化  
 複合ファイルの標準化された構造には、実際には、ファイルを作成したアプリケーションの知識を使用して OLE アプリケーションによって作成された複合ファイルの参照が別の OLE アプリケーションができます。  
  
###  <a name="_core_size_and_performance_considerations"></a> サイズとパフォーマンスに関する考慮事項  
 その他のファイルよりも大きくなります、複雑な複合ファイル記憶域の構造とデータを段階的に保存する機能には、この形式を使用して、ファイルがなる傾向があります。 構造化ストレージの"フラット ファイル"です。 場合、アプリケーション頻繁に読み込みますファイルを保存、複合ファイルを使用する可能性がありますファイルのサイズを増やす普通のファイルよりもはるかに高速です。 大規模な複合ファイルを取得することができます、ため、ファイルのアクセス時刻で格納され、フロッピー ディスクから読み込まれたことができますも影響する、ファイルへのアクセスが遅くなる結果として得られます。  
  
 パフォーマンスに影響する別の問題は、複合ファイルの断片化がします。 複合ファイルのサイズはファイルで使用される最初と最後のディスク セクターの違いによって決まります。 断片化されたファイルは、データは含まれませんが、サイズを計算するときにカウントの空き領域の多くの領域を含めることができます。 複合ファイルの有効期間中は、これらの領域は、挿入、または記憶域オブジェクトの削除によって作成されます。  
  
##  <a name="_core_using_compound_files_format_for_your_data"></a> 複合ファイルの形式を使用して、データ  
 派生したドキュメント クラスを持つアプリケーションを正常に作成する後`COleDocument`のメイン ドキュメント コンス トラクターを呼び出すことを確認`EnableCompoundFile`です。 アプリケーション ウィザードでは、OLE コンテナー アプリケーションを作成したときにこの呼び出しが挿入されます。  
  
 *OLE プログラマーズ リファレンス*を参照してください[IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)、 [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015)、および[ILockBytes](http://msdn.microsoft.com/library/windows/desktop/aa379238)です。  
  
## <a name="see-also"></a>関連項目  
 [コンテナー](../mfc/containers.md)   
 [コンテナー: ユーザー インターフェイスの問題](../mfc/containers-user-interface-issues.md)   
 [関数クラス](../mfc/reference/colestreamfile-class.md)   
 [COleDocument クラス](../mfc/reference/coledocument-class.md)
